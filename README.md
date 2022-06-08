                                         Face Recognition Attendance Management System Using Python
                                         

About the problem: 

The main intention of this project is to solve the issues encountered in the old attendance system while reproducing a brand new GUI based attendance system that can provide convenience to the institution. In this project, an application is created which is capable of recognizing the identity of each individuals and eventually record down the data into a database system. Apart from that, an excel sheet is created which shows the students attendance which can be directly mailed to the respected faculty.

Main objective:

	To develop a GUI integrated attendance system using face recognition to take attendance.
	Registration of new faces and face recognition is to be done manually.
	Password protection for new person registration.
	To show real-time attendance of the day on the screen in a tabular format.
	To develop a Mysql database to save the attendance with id, name date and time
Scope of the project:
	The targeted groups of the attendance management system is the students and staff of an educational institution. 
	The database of the attendance management system can hold lot many individual’s attendance info.
	 The facial recognition process can only be done for 1 person at a time.

 
Working methodology:

![image](https://user-images.githubusercontent.com/77448860/172699029-721bd1a9-0d83-4f2d-9137-12f0c2d7eadb.png)

The Aim of this project is to take attendance using face detection. This program makes CSV file of present attendees automatically after successful face detection. Also, it will make a CSV file for registered 
I made this program using these libraries. OpenCV, Numpy, OS, Pandas, Tkinter, mysql.connector, csv, Datetime 

i) Graphical User Interface:

In this project, I made one simple GUI using the python Tkinter library so that the user can easily use this project without any backend knowledge. Tkinter is the standard GUI library for Python.
For making this GUI. I mainly used Tkinter’s frame, menubar, button, label, message box, table, textbox, etc. I divide my main screen into two parts which are nothing but frames. one is for Registration and the second is for taking attendance.
As shown in the above image this GUI will help users to register new students as well as to take attendance. At the bottom, it will also show you the total number of registered students.
This GUI window also contains menubar with two sub-menu Help and About. The help menu contains 3 commands contact me, change Admin Password, exit.

ii) Take Images:

When users register for new students it will take 100 images of that student and save these images to one folder which will be created at the time of first registration. I use OpenCV to take images and detection.
OpenCV is a library of programming functions mainly aimed at real-time computer vision. I used a cascade classifier of OpenCV for face detection. To use this cascade classifier we need the haarcascade_frontalface_default.xml file which includes all the haar cascade features of a face.
When users want to register new students they have to enter first details like ID and Name. After that, they have to take images of the student for that when the user presses the button ‘Take Images’ webcam will start and it will take 100 images of the student.
There are some methods in OpenCV to take Images. using video frame of OpenCV I’m taking frames and from that, I’m extracting only face images using cascade classifier. After taking images I will store those images in one folder.

iii) Save Profile:

When images will be taken for any student user needs to click the ‘save profile’ button so that it will ask for the admin password. If the admin password was not set it will ask you first to set the admin password or else you need to enter the admin password. This password will be saved in one plan txt file.
If this password is correct then it will call the trainer function which will be going to generate a YML file and it will train our LBPH recognizer using those 100 images. This YML file and password txt file will save in one different folder name “pass_train”.
After saving the profile there are 3 different folders generated in the current directory. Out of those 3 folders, one is containing images of students, the second one is containing a CSV file of student’s details and the third one is containing a pass.txt file and YMLfile.

iv) Taking Attendance:

When a user wants to take attendance and press the ‘Open camera’ button webcam will start and one video frame window will generate to recognize the faces using the YML file. If the face will successfully recognize then it will put the name of the person at the bottom of the rectangle which is showing the detected face area.
After successfully recognized the attendance will be shown in the table in the 2nd frame and the Attandance.csv file will be generated in a particular folder. This CSV file contains the student’s ID, name along with time at which attendance was taken for that student.
Attendance will store in one CSV file. This CSV file will be created datewise i.e attendance of one day is store in one CSV file. If a person will not recognize then in a video capturing it will show unknown. 
Entering Attendance in MYSQL Database: The Attendance will also be stored in the database named ‘facedb’ by python using the library mysql.connector’. A tabular column named “Attendance sheet will be created it contains the id, Name, Date and time of attendance.

vi) Algorithms:

Face Detection using Haar Cascade Classifier:  It is an Object Detection Algorithm used to identify faces in an image or a real time     video. The algorithm uses edge or line detection features proposed by Viola and Jones in their research paper “Rapid Object Detection using a Boosted Cascade of Simple Features” published in 2001. The detection is done using cv.CascadeClassifier. detectMultiScale ( ) method, which returns boundary rectangles for the detected faces. Haarcascade_frontalface_detection.xml file is used to train the classifier for accurate face detection.

Face Recognition using Local Binary Patterns Histograms Recognizer: 

LBPH stands for Local Binary Pattern Histogram, this algorithm is proposed in 2006, It is a basic algorithm that’s used to detect faces from front side. It is used for object as well as face detection. The LBP operator helps to get local features by Local Binary Pattern acts. The local special arrangement of the face is shortened by these LBP acts. The LBP operator divides the face in the image into pixels. Every pixel is associated with 8 neighbor pixels that surroundings it. Each pixel value is then compared with the surrounding neighbor pixel values. Using the LBP combined with histograms we can represent the face images with a simple data vector. The input facial images can be represented in the form of histograms using recognizer.train( ) method. The trained data is stored in the form of .xml file. The recognizer.predict () method will take captured portion of the face to be analyzed as a parameter and will return its probable owner, indicating its id and how much confidence the recognizer is in relation with this match.

Pros:
•	Improvement of security level
•	Easy to use with GUI support
•	It follows  one of the oldest and efficient face recognition algorithms LBPH 
•	It is efficient against monotonic gray scale transformation
•	Works almost real-time on CPU
•	Simple Architecture
•	Detects faces at different scales
Cons:
•	It will require high processing power
•	Processing and Storage of data
•	Doesn’t perform well with unexpected angle of picture or camera
•	Doesn’t work under occlusion	
•	Noisy image can reduce your accuracy so quality of images matter.
•	Doesn’t work on non-frontal images.

#For more information contact
Email:griffintbr@gmail.com

# SCREENSHOTS

Main folder
![image](https://user-images.githubusercontent.com/77448860/172698097-2eb160a3-1428-4a26-92db-cb7e1abe63ce.png)

\TrainingImage
![image](https://user-images.githubusercontent.com/77448860/172698362-43ae2e7c-8470-44ee-815b-e0c31e7c3cf2.png)

\TraningImageLabel
![image](https://user-images.githubusercontent.com/77448860/172698476-909db639-5a89-4e82-8071-399668d652d9.png)

\StudentDetails
![image](https://user-images.githubusercontent.com/77448860/172698572-2cf1eebf-9935-4942-b600-ee9fd636212f.png)

FaceDetection
![image](https://user-images.githubusercontent.com/77448860/172698732-3c2662b4-eebe-4142-bfb4-b95b399323e4.png)

