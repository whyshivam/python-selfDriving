# python-selfDriving
Self-Driving Car working with openCv-python on RaspberryPi

## Ideation
The project is to design and program a functional model of a self-driving car. The model is based on OpenCV-Python and operated on Rasberry Pi, a webcam, and ultrasonic sensors. Arduino is used for power control. The self-driving vehicle featured 
• Edge-detection using neural networks, 
• Signal detection using image processing,
• Steering using move in sdcar.py. 
• Stop sign detection using houghcircles and colour intensities 
• Front collision avoidance using an ultrasonic sensor 
• l298N motor controller 

## Project Structuter          
**sdcar.py** is a combination of all the following :-              
  * **lane_lines.py**:                  
    * **Step1** Take the webcam feed and apply the  canny  edge algorithm to detect the edges                 
    * **Step2** Detect the lines in an edged image using houghlines                  
    * **Step3** Average the lines according to the slope                 
    * **Step4** Making points using slope                  
    * **Step5** Return right, left, camera and central line               
  * **sensor.py**:                 
     distance measurement using input and output pins               
  * **sign.py**:                  
     * Detection of circles in image using hough circles                   
     * If the dominant colour in a square region around the circle is red then it is                    
  * **Stop sign**.                  
     * If the dominant colour in a square region around the circle is blue then 
There are 5 cases left, right, forward, forward and right or forward and left for this:     
       * make the 3 zones of square regions the right , left, upper(for forward)    
       * if the right zone is white and the other two are blue then the sum of RGB colour intensities in the right zone will be obviously greater than the other two zones then the sign is right similarly for others.   

## Prerequisites
You need to have installed following softwares and libraries.
1. Python 3: https://www.python.org/downloads/
2. Anaconda: It will install ipython notebook and most of the libraries which are needed like  pandas, matplotlib, numpy and scipy: https://www.anaconda.com/download/

## Libraries: 
* __Tensorflow:__ It is a deep learning library.
    * pip install tensorflow
* __OpenCV:__ It is used for processing images.
    * pip install opencv-python

       
## Circuitry

You can follow these tutorials as a guide:- 
* [Raspberry Pi motor circuitry](https://business.tutsplus.com/tutorials/controlling-dc-motors-using-python-with-a-raspberry-pi--cms-20051)
* [Raspberry Pi range sensor circuitry](https://www.modmypi.com/blog/hc-sr04-ultrasonic-range-sensor-on-the-raspberry-pi)

Note that you won't be able to follow the tutorials verbatim. One of the tutorials uses a Raspberry Pi 2 whereas I use a 3. The differences are not significant, so you should be able to figure it out. Both tutorials give much better explanations than I can, but if you're curious exactly how I did the wiring, see my diagram below. 

<img width="321" alt="frame" src="https://user-images.githubusercontent.com/8901244/30244462-0e34e4be-9573-11e7-8ea8-81f1203c9492.png">

## Useful Links

* [TensorFlow Timeslines example](https://stackoverflow.com/documentation/tensorflow/3850/measure-the-execution-time-of-individual-operations#t=201707090002297903596 ): Show execution time for each node in your TensorFlow graph
* [Raspberry Pi motor circuitry](https://business.tutsplus.com/tutorials/controlling-dc-motors-using-python-with-a-raspberry-pi--cms-20051): Tutorial for connecting DC motors to your Raspberry Pi
* [Raspberry Pi range sensor circuitry](https://www.modmypi.com/blog/hc-sr04-ultrasonic-range-sensor-on-the-raspberry-pi): Tutorial for connecting an ultrasonic range sensor to your Pi
* [https://www.howtogeek.com/167195/how-to-change-your-raspberry-pi-or-other-linux-devices-hostname/](https://www.howtogeek.com/167195/how-to-change-your-raspberry-pi-or-other-linux-devices-hostname/): Tutorial to give your Pi a hostname so that it's easier to find on wifi
* [http://docs.donkeycar.com/](http://docs.donkeycar.com/) Docs for DonkeyCar, a DIY Meetup group in San Francisco. 
* [http://docs.donkeycar.com/](https://github.com/otaviogood/carputer): The GitHub repo for the winner of the DIYRobors meetup in San Francisco and Oakland
* [https://makezine.com/projects/build-autonomous-rc-car-raspberry-pi/](https://makezine.com/projects/build-autonomous-rc-car-raspberry-pi/) Donkeycar overview



