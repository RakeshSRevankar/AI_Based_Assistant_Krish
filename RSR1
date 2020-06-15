import pyttsx3
import datetime 
import wikipedia
import speech_recognition as sr
import webbrowser as wb
import os
import pyautogui
import psutil
import sys
import pyjokes
import turtle
import requests


engine=pyttsx3.init()

def speak(audio):

    engine.say(audio)
    engine.runAndWait()


def time():
    Time=datetime.datetime.now().strftime("%I:%M:%S")

    speak(Time)



def date():
    year=int(datetime.datetime.now().year)   
    month=int(datetime.datetime.now().month)
    day=int(datetime.datetime.now().day)
    speak("year is")
    speak(year)
    speak("month is")
    speak(month)
    speak("day is")
    speak(day)



def cpu():
    usage=str(psutil.cpu_percent())
    speak('CPU is at'+usage)
    freq=str(psutil.cpu_freq)
    speak('cpu freq is'+freq)
    battery=psutil.sensors_battery()
    speak('battery is at')
    speak(battery.percent)




def wishme():
    speak("welcome back sir!")
    speak("The Current Time is")
    time()
    speak("the current ")
    date()
    hr=datetime.datetime.now().hour
    if (hr>6 and hr<12):
        speak("good morning sir have a nive day!")
    elif(hr>=12 and hr<18):
        speak("Good Afternoon sir!")
    elif(hr>=18 and hr <24):
        speak("Good evening sir!")
    else:
        speak("Good night sir have a sweet dreams take care")
    speak("i am Krish AI Assistant on your service .Please tell me how can i help you!")



def takecommand():
    r=sr.Recognizer()
    with sr.Microphone() as source:
        print("listening...")
        r.pause_threshold=1
        audio=r.listen(source)

    try:
        print("Recgnizing...")
        query=r.recognize_google(audio,language='en-in')
        print(query)

    except Exception as e:
        print(e)
        speak("say it again")
        return 'None'
    return query       



def sss():
    img=pyautogui.screenshot()
    img.save("G:\python\\scs.png")


def jokes():
    speak(pyjokes.get_joke())

def draw():
    r=turtle.Turtle()
    r.speed(0)

    list1=["purple","red","orange","blue","green"]
    for i in range(0,500):
        r.color(list1[i%5])#bcz five colors
        r.pensize(i/10+1)
        r.fd(i)
        r.left(59)
        r.dot()
      


        
    



if __name__=="__main__":
    wishme()
    while True:
        query=takecommand().lower()
        if 'time' in query:
            time()

        elif 'date' in query:

            date()

        elif 'what can u do for me' in query:
            speak('i can play music , send email,  drawing ,  remmeber your note,date and time , and jokes ')
      

        elif 'wikipedia' in query:
            speak("searching.....")
            query=query.replace("wikipedia","")
            result=wikipedia.summary(query,sentences=2)
            print(query)
            speak(result)
      
        elif 'search in chrome' in query:
            speak('what should i search')
            chromepath='C:\Program Files\Mozilla Firefox'
            search=takecommand().lower
            wb.get(chromepath).open_new_tab(search+'.com')
      
        elif 'remember that' in query:
            speak("what should i remember? ")
            data=takecommand()
            speak("you said me to remember that"+data)
            remember=open('data1.txt','w')
            remember.write(data)
            remember.close()  
      
        elif 'do you know anything' in query:
            remember=open('data1.txt','r')
            speak("you said me to rememberred that "+remember.read())
            
      
        elif 'screenshot' in query:
            sss()
            speak("Done..")
      
        elif 'cpu' in query:
            cpu()

        elif 'joke' in query:
            jokes()

        elif 'what is your name' in query:
            speak('i am Krish A I Assistant')

        elif 'who developed you' in query:
            speak('mr.Rakesh S Revankar ,, his information is placed in command prompt')
            print('https://www.linkedin.com/in/rakesh-s-revankar-34094a191/')

        elif 'draw' in query:
            speak("a sure sir")
            draw()

        elif 'nice' in query:
            speak("thank you")

        elif 'wait' in query:
            speak("ok sir")


        elif 'logout' in query:
            os.system("shutdown -l")

        elif 'shutdown' in query:
            os.system("shutdow /s /t 1")

        elif 'restart' in query:
            os.system("shutdown / / 1") 

        elif 'play song' in query:
            speak('sorry i dont have collections') 
            
      

      
        elif 'offline' in query:
            quit()


