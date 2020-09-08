# Camera Based 2D Feature Tracking
The stats of the detector/descriptor runs are in the spreadsheet "DestDesc.ods"

The top 3 detector/descriptor combinations recommendation for the purpose of detecting keypoints on vehicles, based on the stats gathered are:

1. AKAZE/BRIEF - or AKAZE paired with similar fast descriptors (BRISK, ORB).
2. FAST/ORB - offers fast procesing without sacrificing many keypoints or matches.
3. AKAZE/SIFT - gives the absolut higher amount of matches while taking a fair amount of time.

Depending on priorities, the above list can offer some valid options of detector/descriptor pairs. Overall, the AKAZE detector seems to provide a high amount of keypoints, and when leveraging the efficiency of binary descriptors, it offers the best combination for this exercise. Also, we must take into account that when using AKAZE for both detecting and extracting, OpenCV documentation recommends to "detectAndCompute", instead of doing both processes at different points.

Additionally, while not generating as many keypoints as the top implementation, FAST/ORB did achieve a high amount of keypoints and at the same time showed the fast timing FAST can get when paired with a binary descriptor.

Finally, the SIFT descriptor gets to shine with its ability to provide high-quality features, and although lacking in speed, AKAZE detection got to give this combination a fair performance.

NOTE: Since some descriptors use the same heighborhood size overall, they did not have any variance among their keypoints.