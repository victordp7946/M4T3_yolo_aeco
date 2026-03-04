\# Error Analysis



\## Summary

The model shows \*\*high precision\*\* but \*\*low recall\*\*, consistent with a small dataset and class imbalance. PPE items are often small, occluded, or visually ambiguous.



\## 3 False Positives (FP)

> Replace paths with your own evidence images if needed.



1\. \*\*FP Example 1\*\*

&nbsp;  - \*\*Predicted:\*\* hardhat

&nbsp;  - \*\*Reality:\*\* no hardhat / ambiguous head region

&nbsp;  - \*\*Why:\*\* bright head area or helmet-like color/shape caused confusion.



2\. \*\*FP Example 2\*\*

&nbsp;  - \*\*Predicted:\*\* safety\_vest

&nbsp;  - \*\*Reality:\*\* regular clothing (similar hi-vis color)

&nbsp;  - \*\*Why:\*\* orange/yellow shirts resemble vests under certain lighting.



3\. \*\*FP Example 3\*\*

&nbsp;  - \*\*Predicted:\*\* person

&nbsp;  - \*\*Reality:\*\* background object (machinery/shape)

&nbsp;  - \*\*Why:\*\* human-like silhouettes in cluttered scenes.



\## 3 False Negatives (FN)

1\. \*\*FN Example 1\*\*

&nbsp;  - \*\*Missed:\*\* hardhat

&nbsp;  - \*\*Reality:\*\* hardhat present

&nbsp;  - \*\*Why:\*\* helmet too small (far from camera) / partially occluded.



2\. \*\*FN Example 2\*\*

&nbsp;  - \*\*Missed:\*\* safety\_vest

&nbsp;  - \*\*Reality:\*\* vest present

&nbsp;  - \*\*Why:\*\* vest covered by arms/tools or low contrast.



3\. \*\*FN Example 3\*\*

&nbsp;  - \*\*Missed:\*\* no\_safety\_vest

&nbsp;  - \*\*Reality:\*\* person without vest

&nbsp;  - \*\*Why:\*\* torso not clearly visible or model biased toward vest class.



\## Top 3 Data Improvements (Priority)

1\. \*\*Increase minority classes:\*\* add more labeled examples for `hardhat`, `safety\_vest`, `no\_hardhat`, `no\_safety\_vest` (especially far/occluded cases).

2\. \*\*Balance negatives:\*\* ensure similar count of “with PPE” vs “without PPE” examples per class.

3\. \*\*Add diversity:\*\* different sites, lighting, camera angles, distances, and worker poses; include partial occlusions.

