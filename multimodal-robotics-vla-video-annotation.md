# Multimodal Robotics Data Annotation: Vision-Language-Action (VLA) Video Segmentation & Action Understanding

## Task Type
Multimodal Data Annotation – Robotics Video Segmentation / Vision-Language-Action (VLA)

---

## Task Overview

In this task, annotators analyze a robotics video in which a robot performs a warehouse-style packaging workflow involving dishwashing tablets.

The robot performs the following sequence of actions:

- Detects dishwashing tablets inside a container
- Picks tablets one by one
- Counts tablets sequentially
- Places tablets into a packet
- Verifies the quantity
- Moves the completed packet
- Places the packet onto a rolling conveyor belt

The purpose of this task is to create high-quality Vision-Language-Action (VLA) training data for robotics AI systems.

Annotators must divide the video into meaningful temporal segments and describe the robot’s behavior in detail for each segment.

The annotations help train AI systems for:

- Robotic task understanding
- Sequential action learning
- Embodied AI
- Vision-language grounding
- Human instruction following
- Industrial automation systems

---

## Prompt

Count exactly 50 dishwashing tablets, place them into a packet, and move the completed packet onto the conveyor belt.

---

# Annotation Structure

Each video segment should contain:

| Field | Purpose |
|---|---|
| Scene Context | What exists in the scene before the action starts |
| Predicted Robot Intent | What the robot is likely about to do |
| Current Robot Action | What the robot is actively doing |
| Object Interaction | Which objects are involved |
| State Change | What changes during the segment |
| Outcome Status | Whether the action succeeded or failed |

---

# Example Segment Annotation

## Segment 1

### Timestamp
00:00 – 00:04

### Scene Context

A container filled with dishwashing tablets is positioned on the workstation. An empty packet is located beside the robotic arm, and the conveyor belt remains stationary.

### Predicted Robot Intent

The robot is likely preparing to identify and pick the first dishwashing tablet from the container.

### Current Robot Action

The robotic arm moves toward the container while aligning the gripper above the visible tablets.

### Object Interaction

- Dishwashing tablets
- Robotic gripper
- Container
- Empty packet

### State Change

The robotic arm changes from idle position to active alignment above the container.

### Outcome Status

Success – The robot successfully aligned the gripper with the target tablet.

---

## Segment 2

### Timestamp
00:04 – 00:08

### Scene Context

The robotic gripper is positioned directly above the dishwashing tablets inside the container.

### Predicted Robot Intent

The robot is likely attempting to grasp a single dishwashing tablet.

### Current Robot Action

The robotic gripper closes around one tablet and lifts it from the container.

### Object Interaction

- Dishwashing tablet
- Robotic gripper
- Container

### State Change

One tablet changes position from inside the container to inside the robotic gripper.

### Outcome Status

Success – The tablet is securely grasped without slipping.

---

## Segment 3

### Timestamp
00:08 – 00:20

### Scene Context

The robot is holding a dishwashing tablet while the packet remains open beside the workstation.

### Predicted Robot Intent

The robot is likely preparing to place the tablet into the packet and continue the counting process.

### Current Robot Action

The robotic arm transfers the tablet toward the packet opening and releases it into the packet.

### Object Interaction

- Dishwashing tablet
- Robotic gripper
- Packet

### State Change

The tablet moves from the robotic gripper into the packet.

### Outcome Status

Success – The tablet is successfully placed into the packet.

---

## Segment 4

### Timestamp
00:20 – 00:40

### Scene Context

Several tablets are already inside the packet while additional tablets remain inside the container.

### Predicted Robot Intent

The robot is likely continuing the repetitive counting and placement process until the target quantity is reached.

### Current Robot Action

The robotic arm repeatedly picks tablets from the container and inserts them into the packet while maintaining the counting sequence.

### Object Interaction

- Dishwashing tablets
- Robotic gripper
- Container
- Packet

### State Change

The number of tablets inside the packet increases progressively.

### Outcome Status

Success – The counting workflow continues consistently without interruption.

---

## Segment 5

### Timestamp
00:40 – 00:45

### Scene Context

The packet contains multiple dishwashing tablets while the robot prepares another placement action.

### Predicted Robot Intent

The robot is likely attempting to place the next counted tablet into the packet.

### Current Robot Action

The robotic arm moves toward the packet, but the tablet slips from the gripper before reaching the packet opening.

### Object Interaction

- Dishwashing tablet
- Robotic gripper
- Packet

### State Change

The tablet falls onto the workstation surface outside the packet.

### Outcome Status

Failure – The tablet slipped from the robotic gripper during placement.

---

## Segment 6

### Timestamp
00:45 – 00:55

### Scene Context

The packet contains the completed set of dishwashing tablets, and the conveyor belt is visible beside the workstation.

### Predicted Robot Intent

The robot is likely preparing to transfer the completed packet onto the conveyor belt.

### Current Robot Action

The robotic arm grasps the filled packet, lifts it, and places it onto the moving conveyor belt.

### Object Interaction

- Filled packet
- Robotic gripper
- Conveyor belt

### State Change

The completed packet changes position from the workstation to the conveyor belt.

### Outcome Status

Success – The completed packet is successfully transferred onto the conveyor belt.

---

# Evaluation Axes

## 1. Temporal Segmentation Accuracy

### Assessment

This axis evaluates whether the video is divided into meaningful action-based segments.

Segments should begin and end when a significant robotic action changes.

### Common Issues

- Incorrect timestamp boundaries
- Segments too fragmented
- Multiple unrelated actions grouped together
- Action transitions missed
- Counting phase not segmented correctly

### Judgment

Incorrect temporal segmentation should be penalized under Temporal Annotation Failure.

---

## 2. Action Recognition Accuracy

### Assessment

This axis evaluates whether the annotator correctly identifies the robot’s actions in each segment.

### Common Issues

- Picking labeled as placing
- Conveyor transfer action missed
- Counting process mislabeled
- Idle motion incorrectly labeled as meaningful action
- Incorrect action sequence

### Judgment

Incorrect action labels should be penalized under Action Recognition Failure.

---

## 3. Object Identification Accuracy

### Assessment

This axis checks whether all important objects are correctly identified throughout the task.

### Important Objects

- Dishwashing tablets
- Packet
- Conveyor belt
- Robotic arm
- Robotic gripper
- Container

### Common Issues

- Missing objects
- Incorrect object naming
- Failure to track objects across segments
- Occluded objects ignored

### Judgment

Missing or incorrect object annotations should be penalized under Object Annotation Failure.

---

## 4. Language Description Quality

### Assessment

This axis evaluates the quality and completeness of the segment descriptions.

Descriptions should clearly explain:

- What the robot is doing
- Which objects are involved
- The action sequence
- Task progress
- Environmental context

### Common Issues

- Descriptions too vague
- Missing important actions
- Hallucinated actions not visible in video
- Incorrect action order
- Repetitive segment descriptions

### Judgment

Poor or incomplete descriptions should be penalized under Language Annotation Quality.

---

## 5. Sequential Consistency

### Assessment

This axis evaluates whether the annotations remain logically consistent throughout the full workflow.

Expected workflow:

1. Detect tablets  
2. Pick tablet  
3. Count tablet  
4. Place into packet  
5. Repeat until target quantity reached  
6. Move packet  
7. Place packet onto conveyor belt

### Common Issues

- Packet transfer occurs before counting completion
- Inconsistent count progression
- Missing transition steps
- Contradictory segment descriptions
- Repeated numbering errors

### Judgment

Logical inconsistencies between segments should be penalized under Sequential Consistency Failure.

---

## 6. Outcome Verification

### Assessment

This axis evaluates whether each segment correctly records the success or failure of the robotic action.

### Common Issues

- Failed grasp labeled as success
- Slipping objects ignored
- Incorrect success labeling
- Failure causes not described
- Incomplete outcome reporting

### Judgment

Incorrect success/failure annotation should be penalized under Outcome Verification Failure.

---

# Overall Evaluation

## Assessment

The final evaluation should consider:

- Whether temporal segmentation is accurate
- Whether robotic actions are labeled correctly
- Whether object annotations are complete
- Whether descriptions clearly explain the workflow
- Whether action outcomes are properly verified
- Whether the robotic workflow remains logically consistent
- Whether the annotations fully represent the robotic task

---

# Overall Conclusion

A successful annotation output should provide a temporally accurate and semantically rich representation of the robotic workflow.

The segmented annotations should allow another AI system to fully understand:

- What the robot is doing
- Which objects are involved
- When actions occur
- Whether actions succeed or fail
- How the task progresses over time

The final annotations should support reliable Vision-Language-Action (VLA) model training for industrial robotics and embodied AI systems.

---

# Conclusion Note Example

The annotation is penalized under Outcome Verification because the failed tablet placement action was incorrectly labeled as successful even though the tablet visibly slipped from the robotic gripper and landed outside the packet. The output is additionally penalized under Sequential Consistency because the packet transfer segment was annotated before the counting process reached the target quantity.
