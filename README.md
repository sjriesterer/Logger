# Logger
Logger class for Android Studio
Samuel Riesterer
2019

Class for logging in Android Studio. Creates a directory in local storage. Exports log statements to file in directory.

To use:

Add to manifest (if you want to export log to file):

    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
    
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
    
Declare as a top level variable:

	lateinit var logger: Logger
	
Init variable in Main Activity:

	logger = Logger(MainActivity mainActivity, String sharedPreferenceKey, String appDirectoryName, Boolean exportLogToFile)
	
Add to Main Activity onStart():

	logger.attemptFolderCreation()
	
To Log:

	Logger.log(Int logType, String TAG, String logMessage)
	
To delete Log:

	Logger.deleteLog()
	
To get Log string:

	Logger.logToString()
