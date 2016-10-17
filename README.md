# Use sensor pir and buzzer for alert detection
# on Raspberry Pi 2

 

    import RPi.GPIO as GPIO
    import time
    pir_sensor = 11                   # at GPIO 11
    piezo = 3                         # at GPIO 3
    GPIO.setmode(GPIO.BOARD)
    GPIO.setup(pir_sensor, GPIO.IN)
    GPIO.setup(piezo, GPIO.OUT)
    while True:
        i=GPIO.input(11)           # pir sensor for input
      
        if i==0:                   # if the condition not active
            
            print ("Motion not detected"),i
       
            GPIO.output(3, 0)      # output buzzer not active
            
            time.sleep(0.1)
        
        if i==1:                   # if the condition active
            
            print ("Motion detected"), i
            
            GPIO.output(3, 1)      #output buzzer active
            
            time.sleep(0.1)

https://pinout.xyz/

https://www.raspberrypi.org/learning/parent-detector/worksheet/

http://raspberrypi.stackexchange.com/questions/46801/use-a-pir-sensor-to-detect-motion-and-activate-a-piezo-speaker

http://thejackalofjavascript.com/rpi-pir-sensor-node-iot-intruder-alert/

https://sourceforge.net/p/raspberry-gpio-python/wiki/install/

http://www.raspberrypi-spy.co.uk/2012/05/install-rpi-gpio-python-library/
