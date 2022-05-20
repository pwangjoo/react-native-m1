# Application
M1 Macbook에서 React-Native bare 앱 시작하기
last updated 2022/05/06

## Starting
### 1. Install Xcode & Android Studio
__Xcode__
1. Accounts > add Apple Account
2. Components > install iOS (recommend latest)
3. Locations > Command Line Tools > Xcode 00.0 (select latest)

__Android Studio ARM__
1. More Actions > AVD Manager > Create Virtual Device
2. Preference > Appearance & Behavior > System Settings > Android SDK > SDK Tools > install Android SDK Command-line Tools (latest)

### 2. Install dependencies
```zsh
% brew tap AdoptOpenJDK/openjdk
% brew install --cask adoptopenjdk14 #java 14 or higher
% brew install watchman cocoapods
% sudo arch -x86_64 gem install ffi #need x86_64 version
% npm install -g @react-native-community/cli #community version recommanded
```
Your final `.zshrc`:
```zshrc
export ANDROID_HOME="/Users/$USER/Library/Android/sdk" #$USER must be specified
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```
### 3. Init Project
```zsh
% npx react-native init MyApp --template react-native-template-typescript
```

__iOS__
```zsh
% cd ios && pod update
```

__Android__
- `android` > generate `local.properties` file > add `sdk.dir=/Users/$USER/Library/Android/sdk` (`$USER` needs to be specified)
```zsh
% cd android && ./gradlew
```


### 4.Run
```zsh
% npx react-native run-android # Android
% npx run-ios # iOS
```
- if unidentified error occurs, run `npx react-native start --reset-cache`
