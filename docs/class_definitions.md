\# Class Definitions (PPE Detection)



\## Scope

Object detection on construction/site images to identify people and key PPE elements.



\## Classes

\### person

\- \*\*Definition:\*\* Any human body (full body or partially visible).

\- \*\*Bounding box:\*\* Enclose the visible body (include head/torso/limbs if visible).

\- \*\*Edge cases:\*\* If only a small part is visible (e.g., half body), still label.



\### hardhat

\- \*\*Definition:\*\* Safety helmet on a person’s head.

\- \*\*Bounding box:\*\* Tight box around the helmet only (not the head).

\- \*\*Edge cases:\*\* If helmet is partially occluded, box the visible part.



\### safety\_vest

\- \*\*Definition:\*\* High-visibility safety vest (reflective/hi-vis).

\- \*\*Bounding box:\*\* Tight box around the vest garment only (do not include arms).

\- \*\*Edge cases:\*\* If vest is open or partially covered, label visible vest area.



\### no\_hardhat

\- \*\*Definition:\*\* Person without a visible hardhat.

\- \*\*Rule:\*\* Label the \*\*head region\*\* (or approximate head/upper head area) when clearly no helmet is present.

\- \*\*Do not label:\*\* If head is not visible / ambiguous.



\### no\_safety\_vest

\- \*\*Definition:\*\* Person without a visible safety vest.

\- \*\*Rule:\*\* Label the \*\*torso/upper body region\*\* when clearly no vest is present.

\- \*\*Do not label:\*\* If torso is not visible / ambiguous.



\## General Labeling Rules

\- Use tight bounding boxes.

\- Label all relevant instances in each image.

\- If uncertain/ambiguous due to occlusion/blur → prefer \*\*not labeling\*\* negative PPE classes.

