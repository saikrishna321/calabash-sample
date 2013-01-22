calabash-sample
===============

Discussion and help - https://groups.google.com/forum/?fromgroups=#!topic/calabash-android/Elm-HzlXULw

Calabash android installation:
https://github.com/calabash-driver/calabash-driver/wiki/Setup

This project is cloned from - https://github.com/calabash-driver/gdg-devfest-zrh

Installation: 
Test ng pluing to eclipse
TestNG - http://beust.com/eclipse


STEPS

1) Clone this repo using git using git clone command.

2) Set path for - CALABASH_DRIVER_APPS enviroment variable.

3) Import project into eclipse.

4) create test server for apk file to be tested using command 'calabash-android build path-to-apk-file' and place the testserver apk into CALABASH_DRIVER_APPS folder.

5) To verify calabash server installation and instrumentation is fine run this command from command line 
adb shell am instrument -e target_package com.sai.samples.views -e main_activity com.sai.samples.views.PickerViewSample -e class sh.calaba.instrumentationbackend.InstrumentationBackend sh.calaba.android.test/sh.calaba.instrumentationbackend.CalabashInstrumentationTestRunner 

6) RUN SELENIUM GRID:
C:\Users\xxx\workspace\greenhouse-android-test\lib>java -Dfile.encoding=UTF-8 -cp "selenium-server-standalone-2.28.0.jar" org.openqa.grid.selenium.GridLauncher -role hub host 127.0.0.1 -port 4444 & sleep 8

7) Run Pickerjavatest.java as testng test



PROBLEMS THAT MIGHT NEED TO BE FIXED:
I will try to put some help on problems face at this blog - http://mytechlifez.blogspot.co.uk/2013/01/calabash-android-driver-java.html
Hope that  helps

M2_REPO need to be added to eclipse -> windows -> preferences -> java -> buildpath
M2_REPO - C:\Users\username\.m2\repository

(to solve errors with dx.jar)
Close eclipse then update tools to Latest anroid sdk tools 21.01 is needed (must be updated from android sdk manager)

When there is this below error resign application using http://www.troido.de/re-sign.jar (this happens when using apk file build on different machine)
java.lang.SecurityException: Permission Denial: starting instrumentation ComponentInfo{sh.calaba.android.test/sh.calaba.instrumentationbac
kend.CalabashInstrumentationTestRunner} from pid=549, uid=549 not allowed because package sh.calaba.android.test does not have a signature
 matching the target com.example.pickerviews2
