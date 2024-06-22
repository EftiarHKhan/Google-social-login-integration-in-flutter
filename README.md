# Google-social-login-integration-in-flutter
## SHA fingerprint key generation:
Step 1: Install the JDK
Download the JDK:

Go to the Oracle JDK download page or the OpenJDK page.
Download the installer for your operating system.
Install the JDK:

Run the downloaded installer.
Follow the on-screen instructions to complete the installation.
Note the installation directory (e.g., C:\Program Files\Java\jdk-xx.x.x).

Step 2: Add the JDK to the System PATH
Open Environment Variables:

Press Win + S and type Environment Variables.
Select "Edit the system environment variables."
Edit System Variables:

In the System Properties window, click on the "Environment Variables" button.
In the Environment Variables window, find the Path variable under the System variables section and select it.
Click the "Edit" button.
Add JDK to PATH:

In the Edit Environment Variable window, click "New".
Add the path to the bin directory of your JDK installation (e.g., C:\Program Files\Java\jdk-xx.x.x\bin).
Click "OK" to close all windows.

Step 3: Verify the Installation
Open Command Prompt:

Press Win + R, type cmd, and press Enter.
Check keytool Version:

In the Command Prompt window, type:
sh
Copy code
keytool -version
You should see the version of the keytool displayed, indicating it is recognized.

Step 4: Run the keytool Command
Prepare the Command:

Ensure you know the path to your debug.keystore. Typically, it is located in the .android directory in your user profile.
Run the Command:

In the Command Prompt, type the following command (replacing <YourUsername> with your actual username):
sh
Copy code
keytool -list -v -alias androiddebugkey -keystore C:\Users\<YourUsername>\.android\debug.keystore
If prompted for a password, the default password for the debug keystore is usually android.
Example Command
If your username is JohnDoe, the command would look like this:

sh
Copy code
keytool -list -v -alias androiddebugkey -keystore C:\Users\JohnDoe\.android\debug.keystore
Troubleshooting
Ensure the Path is Correct:
Make sure the path to the debug.keystore file is correct. You can navigate to the .android directory to verify its existence.

Environment Variable Changes:
If the changes to the environment variables do not take effect, try restarting your computer.

By following these steps, you should be able to successfully run the keytool command and add the fingerprint to the Firebase console.

## If any issue with - keytool : [The term 'keytool' is not recognized as the name of a cmdlet, function, script file, or operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try again]

Open the Terminal in Android Studio:

Open Android Studio.
Navigate to View > Tool Windows > Terminal to open the terminal.
Set the PATH Variable for PowerShell:
Use the following command to set the PATH variable temporarily in the current session:

sh
Copy code

### $env:Path = "C:\Program Files\Java\jdk-22\bin;" + $env:Path

Verify the PATH:
Check if the PATH is set correctly:

sh
Copy code

### echo $env:Path

Run the keytool Command:

Now, you should be able to run the keytool command:

sh
Copy code

### keytool -list -v -alias androiddebugkey -keystore $env:USERPROFILE\.android\debug.keystore


