# FTC-Into-the-Deep-Arm-IK

I have built a rough draft of an FTC (FIRST Tech Challenge) Java Autonomous OpMode to control a 2-jointed robotic arm using inverse kinematics (IK). This program assumes the arm has two rotational joints (shoulder and elbow) and calculates the angles required for the arm to reach a specific (x, y) position in 2D space.


**Assumptions made:**

1. The arm consists of two links of lengths L1 (shoulder to elbow) and L2 (elbow to end effector).

2. The base of the arm is at (0, 0) in 2D space. Measurements must be made in order to set up the correct coordinates relative to the fixed frame (Joint 1)

3. The motors controlling the joints are named shoulderMotor (Joint 1) and elbowMotor (Joint 2). Later on, if needed, we can add precision to the end effector as well.

4. Motors are set up to take angle inputs in degrees (If not, it is advisable to replace with high torque servos).

5. The program uses simple trigonometry (Law of Cosines, etc.) for IK calculations (Edits will be done with more advanced trignometry if ineffective).

**Key Points:**

1. Inverse Kinematics: The calculateJointAngles method computes the angles for the shoulder and elbow joints using the law of cosines and trigonometry.

2. Motor Control: The moveMotorToAngle method converts the target angles into encoder counts, assuming 1440 counts per revolution (adjust based on your motor configuration).

3. Reachability Check: The code checks if the target point is within the arms reach before attempting to calculate angles.

4. Units Consistency: Ensure that the arm segment lengths and target coordinates are in the same units.



**Testing:**

- Verify the encoder counts for your motors and adjust the moveMotorToAngle logic accordingly.

- Test the arms movements with reachable targets before increasing complexity.

   
