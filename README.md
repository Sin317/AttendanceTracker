## Inspiration
The creation of our project is rooted in the everyday challenges observed in educational institutions and professional settings, where the traditional methods of tracking attendance were not only time-consuming but often full of inaccuracies. The idea sparked during a technology conference attended by Shrunjala, where the theme of leveraging artificial intelligence to solve real-world problems was heavily emphasised. Inspired by stories of how technology could streamline tedious processes and enhance efficiency, we saw an opportunity to apply Computer Vision methodologies in a way that could significantly impact classrooms, corporate meetings, and events. This vision was driven by a desire to empower educators, professionals, and organisers by freeing up valuable time and resources that could be better invested elsewhere.

## What it does
The core of our platform is a very user-friendly application that integrates with laptop's camera systems positioned at the entry point of class. As individuals enter the space, our system instantly recognizes their faces, cross-references them with a pre-registered database, and marks their attendance in real-time. This process not only eliminates the need for manual roll calls or sign-in sheets but also significantly reduces the time spent on administrative tasks, allowing educators, corporate professionals, and event organizers to focus on their primary objectives.

## How we built it
There are 6 steps to designing the attendance tracking algorithm:
1. Initialization: The script starts by initializing a video capture object (video_capture) using OpenCV, which accesses the default camera [0] which is the webcam.

2. Face Encodings: It loads images of known individuals and extracts their face encodings using the face_recognition library. These encodings serve as reference templates for recognizing faces later.

3. Processing Loop: The script enters a continuous loop to capture frames from the live video feed. Each frame is resized and converted to RGB format for processing.

4. Face Recognition: Within the loop, it detects face locations and encodings in the current frame. It then compares these encodings with the known face encodings to recognize individuals present in the frame.

5. Attendance Recording: If a recognized face matches one of the known faces, the corresponding name is displayed on the frame, indicating their presence. Additionally, the script records the name and current time in a CSV file for attendance tracking.

6. User Interaction: The attendance system provides real-time feedback by displaying recognized names on the video feed and removing them from the list of students to mark them as present.

## Challenges we ran into
1. We encountered difficulties installing the Python packages due to incompatible versions. We were able to resolve it by using package managers like 'pip' to manage dependencies effectively and resolved conflicts by updating or downgrading certain packages as needed.

2. Initially we faced problems with accurately detecting faces from the live feed of the webcam, possibly due to factors like poor lighting conditions, low webcam resolution, or limitations in the face detection algorithm. We were able to resolve this issue by adjusting the webcam settings for better image quality and optimizing lighting conditions in the environment. 

3. We experienced difficulties while displaying the recognition results and the live video feed on the screen, possibly due to issues with the OpenCV window management functions or the way the output frames were being processed and displayed.  We resolved this issue by ensuring that the OpenCV functions for creating windows and displaying images were correctly implemented. Additionally, we modified the frame processing pipeline to efficiently handle the real-time video feed without causing delays or freezes.

## Accomplishments that we're proud of
1. **Development of a Real-Time Face Recognition System**: Successfully developed and implemented a real-time face recognition system using Python, leveraging libraries such as face_recognition and cv2. This system is capable of processing video input in real-time to detect and recognize faces.
2. **Attendance Tracking Capability**: The system identifies individuals present in the video feed, records their attendance, and stores the data in a CSV file, thus automating the attendance recording process.
3. **Real-Time Feedback and Display**: Implemented real-time feedback by annotating the video feed with identification results, displaying names of recognized individuals on the screen. This feature enhances user interaction and provides immediate visual confirmation of the system's recognition capabilities.
4. **Customizable and Scalable Design**: Designed the system with modularity in mind, allowing for easy expansion of the face database and adaptation to various use cases beyond attendance tracking, such as security and customer identification.


## What we learned
 1. **Technical Proficiency**: We gained hands-on experience with Python and learned how to integrate libraries like face_recognition for facial recognition tasks, OpenCV for video capture and image processing, numpy for numerical computations, and csv for data handling.
2. **Understanding of Face Recognition Concepts**: We learnt about face recognition concepts, including how facial features are encoded and compared for identification purposes. 
3.  **Problem-solving and Debugging**: We enhanced our problem-solving skills through the process of identifying and resolving issues such as dependency conflicts, camera integration problems, and challenges in displaying real-time recognition results.
 4. **Real-time Data Processing**:  We acquired skills in handling real-time data streams, specifically video feeds from a webcam, and processing this data efficiently to perform face detection and recognition without significant delays. Additionally, we learned the importance of frame resizing and color space conversion (BGR to RGB) to optimize performance without compromising the accuracy of face recognition.


## What's next for Attendance Tracker
A detailed analytics of attendance patterns can be conducted with secure data management. Additionally, having robust privacy protections in place ensures that all data is processed with the utmost security and confidentiality in our system. Moreover, our model is unable to recognize the faces of individuals whose images are not present in our system. To overcome this limitation, we can train our model using larger image datasets. This will aid in generalizing our model's capabilities.
