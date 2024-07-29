# CCminer for Termux

Based on: https://github.com/Oink70/CCminer-ARM-optimized

Install latest arm64-v8a Termux: https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk

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


Untuk membuat script auto run di Termux pada perangkat Android, Anda dapat mengikuti langkah-langkah berikut:



Pasang Termux:Boot:

Install Termux
dari Google Play Store atau F-Droid.
Setelah terpasang, buka Termux dan buat direktori untuk Termux
jika belum ada:

```
mkdir -p ~/.termux/boot
```
Pindahkan Script ke Direktori Boot:

Pindahkan script yang telah dibuat ke direktori ~/.termux/boot:

```
mv ~/start.sh ~/.termux/boot/
```
Restart Perangkat:
Restart perangkat Android Anda. Script autorun.sh akan dijalankan secara otomatis setiap kali perangkat di-boot ulang.

Dengan mengikuti langkah-langkah di atas, Anda dapat membuat script yang akan dijalankan secara otomatis setiap kali perangkat Android Anda dinyalakan menggunakan Termux

