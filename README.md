# and_raise_detection📌
This project demonstrates a basic implementation of a "Hand raise detection" mechanism that detects if a person raises their hand in a video using pose estimation. The system uses YOLOv8n-pose for keypoint detection and analyzes wrist-to-shoulder positions to infer raised hands, mapping them to seating positions.  


⚠️ Accuracy is not production-grade due to lack of custom training. See limitations below.  

---

#How it works📌

-Video Upload: You upload a classroom/meeting video to the notebook.
-Model Initialization: Loads YOLOv8n-pose model to detect body keypoints.

Frame-by-Frame Analysis:  
    For each person in a frame:  
    Extracts wrist and shoulder keypoints.  
    Checks if wrist is significantly above shoulder to detect a raised hand.  
    Determines the person's seating zone by mapping their position.  

-Output Generation:  
-Annotates names of hand-raising individuals on the frame.  
-Saves the output to output_hand_detection.mp4.  



**Example Output📌**  
A line of text (Name of the person) is overlaid on the video when a hand raise is detected. The mapping is based on estimated seating zones.  



**❌Limitations**  
Accuracy is suboptimal because:  
  Model is not trained on custom data.  
  YOLOv8n-pose is not fine-tuned for classroom gesture detection.  


Better Alternatives:  
  MediaPipe Hands and MediaPipe Pose might offer better hand tracking accuracy for this use case.  

  
Person Mapping:  
  Seating map is hardcoded and may not work for different layouts or camera angles.  


No Real-Time Support:  
  Currently processes recorded video only; no live stream support.  

