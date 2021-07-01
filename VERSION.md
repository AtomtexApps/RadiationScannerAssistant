# Radiation Scanner Assistant   

* <b> 1.2.8.9</b>   
1. Added OBD diagnostics (66, 67, 68, 70). If the block returns an error (not 0), then RSA goes into "Simple" mode, a dialog appears with information about the error, the same info is written to the log (only in scan mode), and is also displayed in Info. The Info panel itself changes the font color to red
* <b> 1.2.8.8</b>   
1. The order of displaying the readings for the neutron has been changed: now the first is sk.s., then ppm.
* <b> 1.2.8.7</b>   
1. Added a menu item that enables displaying the count rate separately for each block (needed for verification). Since the BDTU does not show the average c.n. for each channel, only instantaneous, then added averaging of readings over 10 measurements
* <b> 1.2.8.6</b>   
1. A switch has been added to the settings, upon activation of which, if a charger is connected to a smartphone or BTU, the application will automatically switch to the "Simple" mode
* <b> 1.2.8.5</b>   
1. When the neutron threshold is exceeded, a corresponding message appears in the message window. The screen turns on if allowed by the user
* <b> 1.2.8.4</b>   
2. Fixed operation of alarm counters for gamma and neutron
* <b> 1.2.8.3</b>   
1. "Automatic file upload to the cloud" renamed to "Upload files to the cloud"
2. In case of neutron overflow, "- - -" is displayed
* <b> 1.2.8.2</b>   
1. Redesigned display in the log: removed unnecessary empty lines; all strings and parameter names are translated (Rus, Eng, Fra, Isp). The parameters are now in alphabetical order (Map -> TreeMap). Added space after date
2. If the threshold is exceeded, "Radiation safety alarm" is written in the info and log.
* <b> 1.2.8.1</b>   
2. Fixed: AC (alarm count) was in English only
3. Fixed: if during an overflow to take out the plug from the BDKG-11M from the BTDU, this led to the application crash
5. Fixed: removed the display of the percentage on the cloud, if the value = 0%
* <b> 1.2.7.48</b>  
1. Fixed: when starting the application, it often immediately said: "Gamma channel not connected", after which it connected normally and already said that it was connected. Enraged. Now, when trying to connect, it waits 20 seconds before saying "not connected"
* <b> 1.2.7.47</b>  
1. Arranged the code for overloading (CommunicationService)
2. For spectrometric mode: any overload triggers "beep alarm"
* <b> 1.2.7.46</b>  
2. A new type of sound signal has been added for the scan mode: at any overload, instead of beeping, the "Beep alarm" is turned on.
* <b> 1.2.7.45</b>  
1. Added overload for spectrometric mode. Added sayIfTimePassed function
2. Fixed: when switching to overload mode, identification was completed EVEN IF IDENTIFICATION WAS NOT STARTED BEFORE THIS
* <b> 1.2.7.44</b>  
1. Added: after disconnecting the overload, return to the 0-th value display mode (dose rate). Only if H-mode has been activated before 
* <b> 1.2.7.42</b>  
2. The phrase "GAMMA_RADIATION_DETECTED" now sounds only once, previously it was pronounced constantly while the threshold is exceeded
* <b> 1.2.7.40</b>  
1. If there is an overload in terms of gamma or dose rate, then when the threshold is exceeded in the scanning mode, identification WILL NOT turn on.
2. Fixed the mode carousel: replaced == max with> = max, otherwise if in mode 3 or 4 you disable Shire in the settings, g_mode did not go to 0 (there will be 4, 5 ... etc. with max == 3 )
* <b> 1.2.7.38</b>  
1. Redesigned overload logic: now if only spectrometric is overloaded, but broadband is connected, then "Gamma overload". If the Shire is overloaded or the Speck is overloaded when the Shire is not connected, then "Dose rate overload"
2. At any overload, identification is disabled
* <b> 1.2.7.37</b>  
1. Added overload: by neutron, by gamma, by WIDE RANGE. Display in the status, in the log, in the place of the "ball" the inscription "OL".
2. In case of gamma overload, the readings are forced to switch to HighDose (if connected). The mode carousel passes readings NOT over the broadband channel.
3. Added: if broadband is not connected, but enabled in the settings, then "- - -" will be displayed (previously displayed zeros)
4. Now if gamma overload, the MD values are colored red, but the wide-range values remain white. SM values are red only in case of overload in wide-range
* <b> 1.2.7.36</b>  
1. When identifying an unknown radionuclide, "Unknown" is pronounced, displayed in the info, written to the log, when the spectrum is opened, it is displayed in the list of found nuclides as "Unknown". The confidence factor for such a nuclide is NOT DISPLAYED. Colored Credibility Line - Full Length, Blue
2. Updated all imports
* <b> 1.2.7.35</b>  
1. Fixed incorrect operation of the Overload. (It was: when triggered, it was constantly written to the log 2-3 times per second) - it was triggered not by the appearance of an overload, but by its presence
2. When overloaded, writes to the log, to info, to the status line
* <b> 1.2.7.34</b>  
1. Added: when tapping on the area of gamma readings, there is now a carousel of five units (previously three): MD, SS, D, MD-Sh, SS-Sh. If no wide range unit is connected, there are only 3 units in the carousel (no wide range unit)
* <b> 1.2.7.33</b>  
1. Added alarm counter for gamma and neutron
2. Added: gamma and neutron overflow is now displayed in info, written to log, when overflow, the corresponding ball blinks (red or blue)
* <b> 1.2.7.32</b>  
1. When you select an account, the account photo is displayed.
2. Changed the labels on the buttons in the log fragment, it was not obvious before what each button does
* <b> 1.2.7.31</b>  
1. Added: while uploading files to the cloud, the percentage of file uploads is displayed
2. Fixed: new English text was displayed as Russian, the cloud icon on the large layout was displayed as very small
* <b> 1.2.7.30</b>  
1. Added check for pressing the "Upload whole folder" button - when the button is pressed, the process of uploading the project folder is started, while the button button stops downloading until the current upload is completed
* <b> 1.2.7.29</b>  
1. Added: you can adjust the speed of the chart (5 gradations) 
