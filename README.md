# Pranshu

import psutil  

import pygame  

pygame.mixer.init()

pygame.mixer.music.load("python audio.mpeg")


def convertTime(seconds):
    minutes, seconds = divmod(seconds, 60)
    hours, minutes = divmod(minutes, 60)
    return "%d:%02d:%02d" % (hours, minutes, seconds)


battery = psutil.sensors_battery()

battery_life = battery.percent
print("Your current battery status:- ", str(battery_life) + "%")

while True:
    
    battery = psutil.sensors_battery()

    battery_life = battery.percent
    if str(battery_life) != '100':

        continue
    else:
        print("Battery percentage : ", battery.percent)
        print("Power plugged in : ", battery.power_plugged)

        print("Battery left : ", convertTime(battery.secsleft))
        print("full charge")
        pygame.mixer.music.play()






