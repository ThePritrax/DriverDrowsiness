
# Driver Drowsiness Detection System

Driver Drowsiness Detection System is a project built using Dlib, OpenCV & Python. 


## Tech Stack

| Tech | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `Dlib` | `library` | Used for computer vision and calculation projects |
| `Open_CV` | `library` | Used in machine learning and detection work |
| `Python` | `language` |  An interpreted high-level general-purpose programming language. |

## Explanation

- Dlib - Library generally used in Machine Learning Projects, specifically image processing

- Imutils are a series of convenience functions to make basic image processing functions such as translation, rotation, resizing, skeletonization, and displaying Matplotlib images easier with OpenCV

- Dlib is much more accurate than opencv for face detection. It is faster and has more functions but we encountered error in case of eye detection since dlib is not very accurate for smaller size detections, hence we decided to incorporate both to avail the features given by both libraries. We still need to check the accuracy of open cv in eye detection. 

- Numpy - Mathematical and array related functions

- ```cap = cv2.VideoCapture(0)```  - Taking an instance of webcam

- ```detector = dlib.get_frontal_face_detector()``` - Inbuilt function of the dlib, gives us the frontal face detector, higher accuracy than opencv's detector

- ```predictor = dlib.shape_predictor("shape_predictor_68_face_landmarks.dat")``` - Used to detect the 68 facial landmarks, used in snapchat filters and Augamented Reality

- ```bash
	def compute(ptA,ptB)
	dist = np.linalg.norm(ptA - ptB)
	return dist
	```
- Calculation of euclidean distance between landmark points using numpy's linear algebra module

- Blinked function - 6 points are detected in the eye, short distance and long distance are calculated by using the previous compute function and then we calculate their ratio, this ratio helps us determine the status of the eye. Ratio - 'Sum of distances of vertical landmarks divided by twice the distance between horizontal landmarks'. 

- if elif snippet - We use the research based experimental values to determine what condition is the person's eye in.
## Resources

- [68-landmark detector data](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

