# Failure Modes in Manga Style Transfer for Multimodal Generative Models
## Task Type
Multimodal AI Evaluation – Manga Style Image Transformation

## Task Overview
In this task, an input image was already provided, and the model was instructed to convert the original image into a manga-style illustration while preserving the subject’s identity, pose, composition, and important visual details.

The evaluation focused on whether the generated output successfully fulfilled the prompt request, maintained consistency with the original image, preserved visual quality, and avoided common AI-generated artifacts.

---

# Evaluation Axes

## 1. Prompt Adherence

### Assessment
This axis evaluates whether the model successfully fulfilled the user’s request to transform the original image into a manga-style illustration.

### Common Issues
- Manga style not fully applied
- Some areas remain overly realistic
- Weak manga-style linework
- Inconsistent stylization across the image
- Background does not match manga aesthetics
- Prompt request only partially fulfilled

### Judgment
If the generated image fails to fully transform the image into the requested manga style, it is marked as an Instruction Following issue.

---

## 2. Source Image Preservation

### Assessment
This axis evaluates whether the generated image remains consistent with the original input image while applying the manga transformation.

### Common Issues
- Coarse likeness changes
- Face shape altered significantly
- Hairstyle or hair color changed incorrectly
- Pose modified unintentionally
- Facial expression inconsistent with original image
- Important accessories or clothing details removed
- Subject no longer clearly recognizable

### Judgment
If the subject’s original identity or major visual structure changes significantly, it is marked as an Original Image Consistency failure.

---

## 4. Visual & Rendering Quality

### Assessment
This axis evaluates the general visual quality and polish of the generated image.

### Common Issues
- Blending inconsistencies
- Blurriness
- Grainy texture
- Noise in facial or background regions
- Weak edge detailing
- Inconsistent shading
- Low image clarity
- Background quality mismatch

### Judgment
If the image contains noticeable rendering or visual quality problems that reduce the overall output quality, it is marked as a Quality Issue.

---

## 3. AI Artifact Detection

### Assessment
This axis evaluates common AI-generated visual artifacts and anatomical failures.

### Common Issues
- Warped fingers
- Distorted anatomy
- Unnatural teeth
- Flat or lifeless eye pupils
- Duplication artifacts
- Extra fingers or limbs
- Facial asymmetry
- Warped accessories or objects
- Deformed hands or facial features

### Judgment
If visible AI-generated artifacts reduce realism, structure, or visual consistency, they are marked under AI Artifacts.

---

# Overall Evaluation

## Assessment
The final evaluation is based on:
- Instruction Following
- Original Image Consistency
- Quality Issues
- AI Artifacts
- Overall user intent fulfillment and viewing experience

## Overall Conclusion
A successful output should fully transform the original image into a consistent manga-style illustration while preserving the subject’s identity and maintaining high visual quality.

Outputs that fail to fully apply the manga style, significantly alter the original subject, contain visual quality problems, or show noticeable AI artifacts are considered partially successful or unsuccessful depending on severity.
