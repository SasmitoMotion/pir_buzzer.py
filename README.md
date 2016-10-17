# pir_buzzer.py
# Use sensor pir and buzzer for alert the detection
# on Raspberry Pi 2
# sensor pir motion detection have 3 output Vcc, Output and Ground
# buzzer for alert have 2 output Vcc and Ground

import RPi.GPIO as GPIO
import time

pir_sensor = 11                   # at GPIO 11
piezo = 3                         # at GPIO 3

GPIO.setmode(GPIO.BOARD)
GPIO.setup(pir_sensor, GPIO.IN)
GPIO.setup(piezo, GPIO.OUT)
while True:
        i=GPIO.input(11)
        if i==0:
            print ("Motion not detected"),i
            GPIO.output(3, 0)
            time.sleep(0.1)
        if i==1:
            print ("Motion detected"), i
            GPIO.output(3, 1)
            time.sleep(0.1)
