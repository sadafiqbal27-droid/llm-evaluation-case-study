# Multimodal Prompt Iteration Workflow

## Overview

This workflow demonstrates how I evaluate and refine AI-generated images through repeated prompt testing, image comparison, issue detection, and ranking.

The goal is not to generate a perfect image immediately. The goal is to create a prompt that produces at least one "sweet spot" image: an image that mostly follows the prompt but still contains 2–3 clear AI issues that can be analyzed and improved.

## Step 1: Initial Prompt Creation

I begin by writing an image-generation prompt with enough detail to guide the model, but not so much complexity that all outputs fail.

After submitting the prompt, the model generates 8 images.

## Step 2: Sweet Spot Selection

I review all 8 images and check whether at least one image has a useful balance:

- It follows the prompt reasonably well
- It contains 2–3 visible AI issues
- The issues are specific enough to analyze and correct

If all images are perfect, the prompt is too easy and must be rewritten.

If all images are poor, the prompt is too complex and must be simplified.

## Step 3: Image Issue Analysis

For the selected image, I identify issues such as:

- Anatomical distortion
- Object inconsistency
- Incorrect details
- Missing prompt elements
- Unwanted changes
- Poor realism
- Low visual quality
- Background or lighting issues

## Step 4: Correction Command

After selecting the image, I write a specific correction command targeting the main issue.

Example:

“Correct the distorted hand while keeping the face, clothing, pose, and background unchanged.”

The correction must be precise. A vague command usually creates new defects.

## Step 5: Iterative Testing

The model may fix the selected issue but introduce new problems in another area.

For example:

- The hand may improve, but the face changes
- The object may be corrected, but the background becomes inconsistent
- The lighting may improve, but the original style is lost

If the same correction does not work after around 5 attempts, I stop repeating it and test another image instead.

The process continues until a maximum of 35 images is reached.

## Step 6: Reference-Based Correction

When needed, I use screenshots or visual references from other generated images to show the model exactly what should be changed or preserved.

This helps guide the correction more clearly than text alone.

## Step 7: Ranking System

After completing the image set, I rank the outputs from 1 to 7.

- Rank 7: Best overall image
- Rank 1: Weakest image
- Ranks 2–6: Grouped based on similar mistakes and overall quality

Images with similar types of errors are grouped together before ranking.

## Step 8: Comparative Analysis

Each image is evaluated across four main axes:

### 1. Instruction Following

How strongly the image fulfills the original prompt requirements.

### 2. Image Consistency

If an original image or reference was used, I check what changed in the generated version and whether important elements were preserved.

### 3. AI Issues

I identify visible AI-generated defects such as distortions, hallucinated objects, unnatural anatomy, or inconsistent details.

### 4. Quality Issues

I assess overall visual quality, including sharpness, realism, composition, lighting, and clarity.

## Final Conclusion

The final evaluation is written from the user’s perspective.

The conclusion explains which image performs best, which issues remain, and whether the final output would satisfy the user’s request.
