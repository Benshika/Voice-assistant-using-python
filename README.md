# Voice-assistant-using-python
My first mini project

import subprocess

import wolframalpha

import pyttsx3

import tkinter

import json

import random

import operator

import speech_recognition as sr

import datetime

import Wikipedia

import webbrowser

import os

import winshell

import pyjokes

import feedparser

import smtplib

import ctypes

import time

import requests

import shutil

from twilio.rest import Client

from clint.textui import progress

from ecapture import ecapture as ec

from bs4 import BeautifulSoup

import win32com.client as wincl

from urllib.request import urlopen

#text to speech

#pyttsx3 and sapi5 , both interfaces are used here

engine = pyttsx3.init('sapi5')

voices = engine.getProperty('voices')

engine.setProperty('voice', voices[1].id)

#'''here 0 for male voice and 1 for female voice'''

def hear():

import speech_recognition as sr

ear = sr.Recognizer()

with sr.Microphone() as sourse:

print("listening...")

audio = ear.listen(sourse)

try:

text = ear.recognize_google(audio)

print(text)

except:

print("i didn't get that...")

hear()

def speak(audio):

engine.say(audio)

engine.runAndWait()

def wishMe():

hour = int(datetime.datetime.now().hour)

if hour>= 0 and hour<12:

speak("Good Morning Mam !")

elif hour>= 12 and hour<18:

speak("Good Afternoon Mam !")

else:

speak("Good Evening Mam !")

assname =("EDITH")

speak("I am your Assistant")

speak(assname)

def username():

speak("What should i call you mam")

uname = takeCommand()

speak("Welcome Madam")

speak(uname)

columns = shutil.get_terminal_size().columns

print("#####################".center(columns))

print("Welcome Mr.", uname.center(columns))

print("#####################".center(columns))

speak("How can i Help you, Mam")

def takeCommand():

r = sr.Recognizer()

with sr.Microphone() as source:

print("Listening...")

r.pause_threshold = 1

audio = r.listen(source)

try:

print("Recognizing...")

query = r.recognize_google(audio, language ='en-in')

print(f"User said: {query}\n")

except Exception as e:

print(e)

print("Unable to Recognize your voice.")

return "None"

return query

def sendEmail(to, content):

server = smtplib.SMTP('smtp.gmail.com', 587)

server.ehlo()

server.starttls()

# Enable low security in gmail

server.login('your email id', 'your email password')

server.sendmail('your email id', to, content)

server.close()

#main functon starts here

if _name_ == '_main_':

clear = lambda: os.system('cls')

# This Function will clean any

# command before execution of this python file 

elif 'reason for you' in query:

speak("I was created as a Minor project by Ayswarya Madam ")

elif 'change background' in query:

ctypes.windll.user32.SystemParametersInfoW(20,0, "Location of wallpaper", 0)

speak("Background changed successfully")

elif 'open discord' in query:

appli = r"C:\\Users\\ayshu\\AppData\\Local\\Discord\\Update.exe"

os.startfile(appli)

elif 'news' in query:

try:

elif "Good Morning" in query:

speak("A warm" +query)

speak("How are you Madam")

speak(assname)

# most asked question from google Assistant

elif "will you be my gf" in query or "will you be my bf" in query:

speak("I'm not sure about, may be you should give me some time")

elif "how are you" in query:

speak("I'm fine, glad you me that")

elif "i love you" in query:

speak("It's hard to understand that feeling for a machine like me")

elif "what is" in query or "who is" in query:

# Use the same API key

that we have generated earlier

client = wolframalpha.Client("API_ID")

res = client.query(query)

try:

print (next(res.results).text)

speak (next(res.results).text)

except StopIteration:

print ("No results")

# elif "" in query:

# Command go here

# For adding more commands
