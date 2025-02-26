# Body_Segmant_detection
The *Dempster Biomechanical Model* is a widely used anthropometric model for estimating human body segment parameters (BSPs), such as segment lengths, masses, and center of mass locations. It is based on cadaver studies conducted by Dempster in 1955. This model divides the human body into *15 segments*, each with specific properties.

### *Steps for Body Segment Detection Using the Dempster Model*
1. *Extract Human Pose from Video*  
   - Use *OpenPose, Mediapipe Pose, or DeepLabCut* to detect keypoints (joints) in the video.  
   - Key landmarks include *shoulders, elbows, wrists, hips, knees, and ankles*.

2. *Estimate Body Segment Positions*  
   - Map the detected keypoints to the *15 body segments*:
     - *Head & Neck*
     - *Upper Arms (Left & Right)*
     - *Forearms (Left & Right)*
     - *Hands (Left & Right)*
     - *Torso*
     - *Thighs (Left & Right)*
     - *Shanks (Left & Right)*
     - *Feet (Left & Right)*

3. *Apply Dempster’s Proportions*  
   - Approximate segment *lengths* using standard human proportions.
   - Estimate segment *masses* as a percentage of total body weight:
     - *Head & Neck* → 8.1%  
     - *Torso* → 50.1%  
     - *Upper Arm* → 2.71% each  
     - *Forearm* → 1.62% each  
     - *Hand* → 0.61% each  
     - *Thigh* → 10.5% each  
     - *Shank (Lower Leg)* → 4.33% each  
     - *Foot* → 1.37% each  

4. *Visualize the Body Segments*  
   - Overlay *line segments* between detected keypoints.
   - Display segment mass centers based on *Dempster’s Center of Mass (CoM) positions*.
   - Example:  
     - The CoM for the *forearm* is about *43% from the elbow towards the wrist*.  
     - The CoM for the *shank (lower leg)* is *43% from the knee towards the ankle*.  

5. *Calculate the Center of Gravity (CG) Path*  
   - Compute the *whole-body CG* by weighting each segment’s CoM.
   - Plot the CG trajectory *directly on the video*.

6. *Generate Graphs for Movement Analysis*  
   - *Horizontal & Vertical Position Graphs* for each segment.  
   - *Total Distance Moved* by key segments.  

---

### *Tools & Libraries for Implementation*
- *Pose Estimation*: OpenPose, MediaPipe, DeepLabCut  
- *Programming Language*: Python  
- *Libraries*: OpenCV, NumPy, Matplotlib, SciPy
