#!/bin/bash

main() {
    echo -e "Downloading Latest Roblox"
    local version="version-24b06fe4fe1c4c9d"
    curl "http://setup.rbxcdn.com/mac/$version-RobloxPlayer.zip" -o "./RobloxPlayer.zip"

    echo -e "Installing Latest Roblox"
    [ -d "/Applications/Roblox.app" ] && rm -rf "/Applications/Roblox.app"
    unzip -o -q "./RobloxPlayer.zip"
    mv ./RobloxPlayer.app /Applications/Roblox.app
    rm ./RobloxPlayer.zip

    echo -e "Downloading MacSploit Optimized"
    curl -O "https://raw.githubusercontent.com/Nexus42Dev/MacSploit/main/MacSploit.zip"

    echo -e "Installing MacSploit Optimized"
    unzip -o -q "./MacSploit.zip"

    echo -e "Customizing Roblox"
    mv ./macsploit.dylib "/Applications/Roblox.app/Contents/MacOS/macsploit.dylib"
    ./insert_dylib "/Applications/Roblox.app/Contents/MacOS/macsploit.dylib" "/Applications/Roblox.app/Contents/MacOS/RobloxPlayer" --strip-codesig --all-yes
    mv "/Applications/Roblox.app/Contents/MacOS/RobloxPlayer_patched" "/Applications/Roblox.app/Contents/MacOS/RobloxPlayer"
    rm ./insert_dylib

    echo -e "Installing MacSploit App"
    [ -d "/Applications/MacSploit.app" ] && rm -rf "/Applications/MacSploit.app"
    mv ./MacSploit.app /Applications/MacSploit.app
    rm ./MacSploit.zip

    echo -e "Install Completed! Developed by Nexus42, Optimized by forensnoway."
}

main
