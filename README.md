# python_openCV_Lines_Rect_Circle_Text

import numpy as np
import cv2 as cv

cap = cv.VideoCapture(0)

while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    img = cv.line(frame, (0,0), (width,height), (255,124,0), 10)
    img = cv.line(img, (width,0), (0,height), (50,0,255),10)
    img = cv.rectangle(img, (50,50), (600,400), (189,255,189),10) 
    img = cv.circle (img, (250,200), 50, (200,100,170), -1) #pass thickness as -1 to fill the circle
    txt = cv.putText (img, "Dhuha is great!", (40,height-20), cv.FONT_HERSHEY_SIMPLEX, 2, (80,15,69), 2, cv.LINE_AA)
    cv.imshow("frame",frame)
    if cv.waitKey(1) == ord("q"):
        break


cap.release()
cv.destroyAllWindows()
