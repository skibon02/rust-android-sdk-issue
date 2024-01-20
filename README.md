This is a minimal test application based on `GameActivity` that just
runs a mainloop based on android_activity::poll_events() and traces
the events received without doing any rendering. It also saves and
restores some minimal application state.

```
export ANDROID_NDK_HOME="/home/skygrel19/Android/Sdk/ndk"
export ANDROID_HOME="/home/skygrel19/Android/Sdk"

rustup target add aarch64-linux-android
cargo install cargo-ndk

cargo ndk -t arm64-v8a -o app/src/main/jniLibs/ --platform 31 build
./gradlew build
./gradlew installDebug
adb shell am start -n co.realfit.agdkmainloop/.MainActivity
```
