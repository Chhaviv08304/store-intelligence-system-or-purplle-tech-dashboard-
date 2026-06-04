# Engineering Choices and Trade-offs

## 1. Object Detection and Tracking
- **Choice:** YOLO (v8) + ByteTrack/DeepSORT.
- **Trade-off:** We prioritized speed/real-time processing over absolute theoretical precision. YOLO combined with a robust tracker handles occlusions fairly well while maintaining high FPS, which is critical for real-time video intelligence.

## 2. Framework Choices
- **Backend:** FastAPI (Python). Chosen for high performance with async support and ease of building REST endpoints quickly.
- **Frontend:** React + Vite. React provides a component-driven architecture for a live dashboard, and Vite offers excellent build times.

## 3. State Management & Event Handling
- **Choice:** In-memory tracking and event aggregation for simplicity in this challenge.
- **Trade-off:** Using Redis or Kafka would make the system more scalable for multiple camera feeds, but for a standalone dockerized submission, keeping state in a simple service or SQLite database minimizes infrastructure complexity and setup failure risks.

## 4. Double Counting & Re-entry Logic
- **Choice:** Session-based counting. A person who exits and re-enters within a short time window (e.g., 2 minutes) is counted as one visitor.
- **Trade-off:** Requires retaining short-term memory of tracked IDs, but provides a much more accurate translation of raw signals into business reality.

## 5. Staff Filtration
- **Choice:** Assumption-based zone logic or appearance heuristic. Since actual staff labels aren't provided, we filter based on dwell areas (e.g., remaining behind the checkout counter for >X minutes) or high-frequency crossing of the entry zone without dwell.
