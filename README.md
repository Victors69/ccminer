# CCminer for Termux

Based on: https://github.com/Oink70/CCminer-ARM-optimized

Install latest Termux: 
https://f-droid.org/id/packages/com.termux/



Proceed with installation, configuration & compilation:

1. Installing clang and dependencies:
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson build-essential clang binutils git
```

2. Fix environment & clone repo:
```
cp /data/data/com.termux/files/usr/include/linux/sysctl.h /data/data/com.termux/files/usr/include/sys
git clone https://github.com/Victors69/ccminer.git
cd ccminer
chmod +x build.sh configure.sh autogen.sh start.sh
```

3. Edit Arch & Cores:
```
nano configure.sh
```

4. Compile ccminer:
```
CXX=clang++ CC=clang ./build.sh
```

5. Change your pools, address, and miner name with:
```
nano config.json
```

6. Finally run the miner with:
```
~/ccminer/start.sh
```
 

# Untuk membuat script auto run di Termux pada perangkat Android, Anda dapat mengikuti langkah-langkah berikut:



Pasang Termux:Boot: https://f-droid.org/en/packages/com.termux.boot/

1. Grant Permissions

Ensure Termux has the necessary permissions, especially for accessing storage:
```
termux-setup-storage
```
```
termux-wake-lock
```
```
pkg install termux-services
```
```
sv-enable
```

2. Set Up the Boot Script
```
mkdir -p ~/.termux/boot
```
3. Create a new script file in the .termux/boot directory:
```
nano ~/.termux/boot/startup.sh
```
4. Add your desired commands to the script. For instance:
```
#!/data/data/com.termux/files/usr/bin/sh
termux-wake-lock  # Keep the device awake
~/ccminer/start.sh
```
5. Set the appropriate permissions for the script:
```
chmod +x ~/.termux/boot/startup.sh  
```

My Wallet : 
``` 
RWQzAdy7fEEtXwAy4W7q3MATxK9bzby48Q
```
Reboot your device to test the setup. After rebooting, Termux
should automatically execute your script......
























