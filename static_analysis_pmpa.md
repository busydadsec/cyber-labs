Manual static analysis

PS C:\Users\benkl\OneDrive\Desktop\PMPA> location of injuredandroid.apk for manual static analysis using apktool

PS C:\Users\benkl\OneDrive\Desktop\PMPA> apktool d .\injuredAndroid_pulled.apk -r [Mean don't decompile]
  PS C:\Users\benkl\OneDrive\Desktop\PMPA> apktool d injuredAndroid_pulled.apk <-- NOT GOING TO USE -r RIGHT NOW SO NOW GOING TO DECOMPILE

  .so <-- File type means shared object. example libapp.so dev's hide api keys here always worth a look. 

  You use apktool to decompile the application in order to add changes to the application. 
  You can use JADX to analyse the app but in order to actually make changes and then recompile for it to be used you need to decompile using apktool. Example patching frida in etc.  

How to find hardcoded strings

In JADX go to resources -> resources arsc -> res -> values -> attrs.xaml = the attributes xml for the UI 

resources -> resources arsc -> res -> values -> strings.xml = this has a lot of hardcoded strings

  <resources>
    <string name="AWS_ID" />
    <string name="AWS_SECRET" />
    <string name="FlagFourText">Flag Four - Login 2</string>
    <string name="FlagOneText">Flag One - Login</string>
    <string name="FlagThreeText">Flag Three - Resources</string>
    <string name="FlagTwoText">Flag Two - Exported Activity</string>
    <string name="abc_action_bar_home_description">Navigate home</string>
    <string name="abc_action_bar_up_description">Navigate up</string>
    <string name="abc_action_menu_overflow_description">More options</string>
    <string name="abc_action_mode_done">Done</string>

  This is self-explanatory. 

  Also look for client ID's URL's etc. 

   <string name="flags_overview">Flags Overview</string>
    <string name="gcm_defaultSenderId">430943006316</string>
    <string name="google_api_key">AIzaSyCUImEIOSvqAswLqFak75xhskkB6illd7A</string>
    <string name="google_app_id">1:430943006316:android:d97db57e11e42a1a037249</string>

  Again self-explanatory. Kepp looking through the file and use the ctl F to find all things such as API, user, ID, password, AWS, secret, http, https, etc.
  Could be something in integers.xml or xmls.xml etc. Use the magic wand text search. 
  
  Searches the whole source code with the wizard. Very useful. 
  ClientID Key, all worth searching for. 
  Have a holistic look at the app. 

  Next I will look at Injured Android Static Anlysis Flags 1-4. 
  
