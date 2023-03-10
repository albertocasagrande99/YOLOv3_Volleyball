# Detection and tracking in volleyball match :mag:
Our software detects the players and the ball in volleyball games. Furthermore, it is possible to track the ball within a video of a match. The detector used is YOLOv3, while the tracker is CSRT, which is available in OpenCV. 

## Weights
### Player detection
In order to perform the player detection we used yolov3's default weights, which can be downloaded at the following [link](https://pjreddie.com/media/files/yolov3.weights).
### Ball detection
Regarding ball detection, Yolov3 was trained specifically for volleyball using a [custom dataset](https://drive.google.com/file/d/1NUJIKjXq0BO84ipHVLFN9xxuy0RfRaWg/view?usp=sharing), and the weights created can be downloaded from this [link](https://drive.google.com/file/d/134TUXIisUhudCI5CO8rZinv-CR9K7P_r/view?usp=sharing).

## How to run
:hammer_and_wrench: `Opencv-contrib-python version 4.4.0.46`
### Player detection :water_polo:
```
python player_detection.py -l obj_person.names -cfg yolov3.cfg -w yolov3.weights -v video.mp4 -s -out_txt video.txt
```
### Ball detection :volleyball:
```
python ball_detection.py -l obj_ball.names -cfg yolov3_custom.cfg -w yolov3_custom_last.weights -v video.mp4 -s -out_txt video.txt
```
### Ball tracking :volleyball:
```
python ball_tracker.py --det video.txt --video video.mp4 --out_tracker tracker_output.txt
```
