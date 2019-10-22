
# Android POC Architecture

## Architecture 1 (Direct communication using NDK Layer)
![Architecture 1](Images/Image1.png)

* The Android application for GE appliance is developed using Android SDK. This Android App makes use of Named Pipe(FIFO) to communicate with GEA Application.
This Pipe code is written as Native Code(C/C++)  
**Note: Android studio 3.4.1 and Android NDK tool is used for developing Android Application**
* Since Android App is written in Java hence system services provided by android cannot use APIs of Native Code (C/C++) directly.  
To solve this issue Android provides JNI and Android NDK which allow to use Native code API.  
* GEA Application code implements GEA task/thread which initializes GEA Bus. GEA Application code also implements UART configuration code for GEA3 communication. This code implements API’s required by GE appliance common code library to send and receive data over UART.  
This GEA Application run at Android Bootup.  
* GE appliance common code module which is provided by GE is written in Native language i.e. C. This module is common for all the appliances hence to provide interoperability and reusability, a static library is created using this code. This library is part of GEA Application code.  

## Architecture 2 (Using Android Services and Service Manager)
![Architecture 2](Images/Image2.png)

* The Android application (apk) for GE appliance is developed using Android SDK. This Android App makes use of API’s exported by GEA Device Manager and GEA services.
* GEA Device Manager and GEA device Manager Services are part of Java framework and acts as interface between low level GEA Application code and GEA App (apk). To access any functionality of GEA code, android app will start these services at Android framework layer.
* GEA Application code implements GEA task/thread which initializes GEA Bus and exports functionalities using which Android application can perform GEA3 communication.  
For e.g. provide functionality to read ERD, write ERD, subscribe to ERD etc.  
* GEA Application code also implements UART configuration code for GEA3 communication. This code implements API’s required by GE appliance common code library to send and receive data over UART.  
GEA Application code will run as a user-space process in Linux and GEA HAL will communicate with it using IPC mechanism (Named Pipe)
* GE appliance common code module which is provided by GE is written in Native language i.e. C. This module is common for all the appliances hence to provide interoperability and reusability, a static library is created using this code. This library is part of GEA Application code.  

