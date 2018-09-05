# **BASIC ASSISTANT ACTIONS**

_Copyright (c) 2018 Google Inc. All rights reserved._

Basic Assistant Actions is a reference open-source project that demonstrates to Google OEM partners which Android Intents, Data, and Parameters the Assistant generates to fulfill user initiated actions though an Android device-resident application.

## Overview

Basic actions consist of actions that should already work on most devices. Basic actions use Android framework APIs and public Android intents. No private parameters or new framework APIs are required. These intents are issued by the Assistant to fulfill users' spoken requests. 

Basic Assistant Actions allows users to view basic action intent content and extra parameter. This intent is being sent to the Android system from Assistant while we give commands to the assistant with saying "Take a photo" , "Set an alarm" or some other basic actions defined below

### Applied Basic Actions
Applied basic actions can be implemented by including the corresponding intents and categories in the AndroidManifest.xml file. Some intents include data and extras.

Call (number or contact)

Set alarm (absolute and relative time)

Cancel alarm

Set timer (absolute and relative time)

Take a note

Take a picture (duration and camera selection)

Open a webpage

Show alarms

Show contacts

### Note: 
The Google Assistant makes a distinction between the command "Show" and the command "Open." The command "Show" displays information on the screen, within the Google Assistant interface when possible. The command "Open" searches for an app and launches the app if found.

For example, "Show my contacts" displays a list of contacts synced to a user's Google Account. "Open my contacts" tries to find an app named "Contacts" and launch that app.


## Examples

### Take a picture

Users should be able to take a picture using either the front or back camera on their device. They should also be able to specify a delay, in seconds, before devices take the pictures.

Intent	android.media.action.STILL_IMAGE_CAMERA

Category	android.intent.category.DEFAULT

Data	-

### _Received extra_	

android.intent.extra.TIMER_DURATION_SECONDS (Int - default: 3)

com.google.assistant.extra.TIMER_DURATION_SECONDS (Int - default: 3)

com.google.assistant.extra.USE_FRONT_CAMERA (Bool - default: true)

android.intent.extra.USE_FRONT_CAMERA (Bool - default: true)

Example invocations	"Take a picture."

"Take a picture in 3 seconds."

"Take a selfie."

"Take a selfie in 3 seconds."

Example received extra	Take a picture

N/A

Take a picture in 3 seconds

android.intent.extra.TIMER_DURATION_SECONDS returns 3

com.google.assistant.extra.TIMER_DURATION_SECONDS returns 3

Take a selfie

com.google.assistant.extra.USE_FRONT_CAMERA returns true

android.intent.extra.USE_FRONT_CAMERA returns true

Take a selfie in 3 seconds

android.intent.extra.TIMER_DURATION_SECONDS returns 3

com.google.assistant.extra.TIMER_DURATION_SECONDS returns 3

com.google.assistant.extra.USE_FRONT_CAMERA returns true

android.intent.extra.USE_FRONT_CAMERA returns true


### _AndroidManifest.xml:_
 
  < intent-filter>

  < action android:name="android.media.action.STILL_IMAGE_CAMERA" />

  < category android:name="android.intent.category.DEFAULT" />

  < /intent-filter>



## Launching Application

To see intent content, application doesnt have to be launched. 

- Close application
- Open Assistant or say "Ok Google"
- When assistant launched , say "Take a selfie"
- Basicactions (compiled Basic Assistant Actions) will start automatically 



## Support
hzulmez@google.com
