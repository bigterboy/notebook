# NOTEBOOK

> NOTE FOR CONFIG

1. Config for android home 
https://stackoverflow.com/questions/38835931/react-native-adb-reverse-enoent
`open .bash_profile`
`open ~/.zshrc`
`touch ~/.zshrc`

Add this to zshrc

export JAVA_HOME=/Applications/Android\ Studio.app/Contents/jre/Contents/Home
export ANDROID_HOME=/Users/<your_computer_name_here>/Library/Android/sdk
export PATH=$ANDROID_HOME/emulator:$PATH
export PATH=$ANDROID_HOME/platform-tools:$PATH
export PATH=$ANDROID_HOME/tools:$PATH
export PATH=$ANDROID_HOME/tools/bin:$PATH

And Last thing to do will be compile `source ~/.zshrc`



