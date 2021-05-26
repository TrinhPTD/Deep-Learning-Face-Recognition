# Deep-Learning-Face-Recognition

Authors: Trinh Phan, Maryam Taherirani, Taylor Murray

## Introduction
Facial recognition has been in our sights since the 1960s while the first webcam was not used until 1991
by Cambridge University to monitor their coffee pot. Our needs as a culture have evolved, so our
technology must become more innovative. For example, teachers are the unsung heroes of today's world.
Classes are getting bigger. Teaching methods are being forced to change due to the recent pandemic.
Teachers are adapting both in their teaching methods and administrative portions of their jobs. Our
product provides an implementation of Super-Resolution & Facial Recognition for attendance. We strive
to deliver a system that will recognize the participants, whether they are students, employees working
from home, volunteers, or any individual trying to keep track of attendance. This is all done via webcam
so it is easy and provides accurate results while also following social distancing guidelines. Rollcall will
push taking roll to the next level. It will allow users to seamlessly keep track of attendance with minimal
manual work on their part.

## Data and Process
Dataset of attendance is created before the recognition process for training purposes. We have created
a dataset of 3 students that include their names and images of the student.
This project is an adaptation of a Face Recognition project designed by Murtaza Hassan. 

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/1.Face%20recognition%20diagram.PNG?raw=true">

## Super Resolution
EDSR (Enhanced Deep Residual Networks for Single Image Super-Resolution) model is used for the
super-resolution part. The model for single image super-resolution looks like the one shown.

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/2.EDSR%20Model.PNG">

Then, the EDSR model is defined by considering the scale, the number of filters, and the number of
residual blocks as its input. Residual block and upsampling functions also need to be defined by
considering filters, number of filters, and scale. Then, model components showing the efficient sub-pixel
convolution has been shown in the following. The input of this model is a low-resolution image, and its
output is the high-resolution version of the input image.

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/3.SR%20model.PNG">

For our research, the number of residual blocks is considered to 16 super-resolution factors. Scale and
number of filters are fixed to 4 and 64, respectively. Finally, the super-resolution image is created, and LR
and SR images are compared together. The SR image is now saved in order to be used as the input for further analyses.

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/4.SR%20output.PNG">

## Face Recognition
First, we create an attendance database, which contains three pictures of ourselves. We use the output
from resolution as the train image for this process and use other pictures as test photos.

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/5.Face%20recognition%20data.PNG">

Next, we locate the face in our photos and embed code and compare the distance between the
training and test photos. The lower distance indicates a better match with the train photos.
From a distance, we can identify the person. As you can see, the distance of the right picture is higher
in value than the left picture. So, the match result is false, while the other shows true.

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/6.Face%20verification.PNG">

Finally, we check the attendance by using the webcam to capture the photos then compare with the
photos from the database to see whether it successfully recognized the person. Then, the entry time is
recorded. The attendance of recognizing images of students is marked in real-time. Additionally, import
to excel sheet and saved by the system automatically.
<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/7.Attendance_camera.PNG">

<img src="https://github.com/TrinhPTD/Deep-Learning-Face-Recognition/blob/main/images/8.Attendance%20list.PNG">

## Conclusion
This product is useful for many audiences. As mentioned earlier, teachers would be able to cut back time
spent on taking attendance while also maintaining accuracy. This is a useful concept both in distance
learning and in-person because it allows for safe social distancing. Employers can use it to maintain
employee attendance both in the office and working remotely. This will obviously help hold employees
accountable, thus increasing the efficiency of a business. Time is money, so taking the time spent in
attendance down to a minimum should be a priority for everybody. One of the limitations of the current
project is that we use one picture for a person and then use that same photo to check with a camera. In
the future study, this system needs to be improved by adding more photos with different poses and
variances for training.
