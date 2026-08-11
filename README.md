# Sara - Android AI Assistant 🤖

Sara is a personal AI voice assistant for Android that enables hands-free control of your device through voice commands and text-based chat.

## Features

- 🎤 **Voice Input** - Speak commands naturally to Sara
- 🔊 **Voice Responses** - Get audio feedback for all commands
- 💬 **AI Chat Interface** - Type or speak commands and get instant responses
- 📱 **App Launcher** - Open installed apps using voice: "Sara, open YouTube"
- ⚙️ **Settings Access** - Quick access to Android settings
- 🕐 **Time & Date** - Ask "What time is it?" or "What's the date?"
- 🔐 **Permission-Based** - Only requests necessary permissions
- 🛡️ **Privacy-Focused** - No hidden access or spyware

## Example Commands

```
"Sara, open YouTube"
"Sara, open WhatsApp"
"Sara, open Chrome"
"Sara, open Facebook"
"Sara, open Settings"
"What time is it?"
"What is the date?"
"List apps"
```

## Project Structure

```
sara-android-assistant/
├── app/
│   ├── build.gradle
│   ├── proguard-rules.pro
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml
│       │   ├── java/com/sara/assistant/
│       │   │   ├── MainActivity.java
│       │   │   └── SaraCommandProcessor.java
│       │   └── res/
│       │       ├── layout/
│       │       │   └── activity_main.xml
│       │       ├── values/
│       │       │   ├── colors.xml
│       │       │   ├── strings.xml
│       │       │   └── themes.xml
│       │       └── xml/
│       │           ├── backup_rules.xml
│       │           └── data_extraction_rules.xml
├── gradle/
│   └── wrapper/
│       └── gradle-wrapper.properties
├── .github/
│   └── workflows/
│       └── build-apk.yml
├── build.gradle
├── settings.gradle
├── gradlew
├── gradlew.bat
└── README.md
```

## Requirements

- **Android SDK**: API 24+ (Android 7.0)
- **Target SDK**: API 34 (Android 14)
- **Java**: Version 1.8+
- **Gradle**: 8.0+

## Permissions

Sara requests only the following permissions:

- `RECORD_AUDIO` - For voice input/speech recognition
- `INTERNET` - For speech recognition services
- `QUERY_ALL_PACKAGES` - To show and launch installed apps

No hidden or excessive permissions are requested.

## Building the Project

### Using Android Studio

1. Open Android Studio
2. Click "Open an Existing Project"
3. Select the `sara-android-assistant` directory
4. Wait for Gradle to sync
5. Click **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**

### Using Command Line

```bash
# Build debug APK
./gradlew assembleDebug

# Build release APK
./gradlew assembleRelease

# The APK will be located at: app/build/outputs/apk/
```

## GitHub Actions Build

This project includes a GitHub Actions workflow that automatically builds a debug APK on every push.

**Workflow File**: `.github/workflows/build-apk.yml`

The workflow:
- Triggers on every push to any branch
- Sets up Java environment
- Builds a debug APK
- Uploads the APK as an artifact

View build artifacts:
1. Go to **Actions** tab in the repository
2. Click on the latest workflow run
3. Download the APK from "Artifacts"

## Running on Device

### Prerequisites

- Android device with API 24+ (Android 7.0)
- USB debugging enabled
- Connected via USB to your computer

### Installation

```bash
# Install debug APK
./gradlew installDebug

# Or manually install
adb install app/build/outputs/apk/debug/app-debug.apk
```

## App Information

- **App Name**: Sara
- **Package ID**: com.sara.assistant
- **Min SDK**: API 24 (Android 7.0)
- **Target SDK**: API 34 (Android 14)
- **Current Version**: 1.0.0

## Architecture

### MainActivity.java
- Main UI activity
- Handles voice input using Android's Speech Recognition API
- Manages text-to-speech for voice responses
- Processes user input and displays output
- Requests and manages permissions

### SaraCommandProcessor.java
- Processes voice and text commands
- Handles app launching via Android intents
- Provides time and date information
- Lists installed applications
- Executes system commands (Settings access)

## Privacy & Security

- ✅ No telemetry or analytics
- ✅ No data collection
- ✅ No hidden permissions
- ✅ Open source (visible code)
- ✅ All processing happens locally
- ✅ Minimal required permissions only

## Troubleshooting

### Build Issues

**Error: "SDK location not found"**
```bash
# Create local.properties with Android SDK path
echo "sdk.dir=/path/to/android/sdk" > local.properties
```

**Error: "Gradle sync failed"**
```bash
# Clean build
./gradlew clean build
```

### Runtime Issues

**No microphone access**
- Ensure RECORD_AUDIO permission is granted
- Go to: Settings → Apps → Sara → Permissions → Microphone

**Voice commands not working**
- Ensure device has an active internet connection
- Check that speech recognition is enabled on device
- Verify microphone is working

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

This project is open source and available under the MIT License.

## Support

For issues, feature requests, or questions:
1. Check existing GitHub issues
2. Create a new issue with detailed information
3. Include device model, Android version, and steps to reproduce

---

**Made with ❤️ by the Sara Team**
