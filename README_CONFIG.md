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



node -v > .nvmrc

.zshrc

# place this after nvm initialization!
autoload -U add-zsh-hook
load-nvmrc() {
  local node_version="$(nvm version)"
  local nvmrc_path="$(nvm_find_nvmrc)"

  if [ -n "$nvmrc_path" ]; then
    local nvmrc_node_version=$(nvm version "$(cat "${nvmrc_path}")")

    if [ "$nvmrc_node_version" = "N/A" ]; then
      nvm install
    elif [ "$nvmrc_node_version" != "$node_version" ]; then
      nvm use
    fi
  elif [ "$node_version" != "$(nvm version default)" ]; then
    echo "Reverting to nvm default version"
    nvm use default
  fi
}
add-zsh-hook chpwd load-nvmrc
load-nvmrc
