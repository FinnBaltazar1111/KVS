# kvs
KVS: Kernel Version Switcher, made to easily switch the tpm_kernver for Chromebooks.

## Build Instructions
1) Clone the repo: <br />
```
git clone https://github.com/kxtzownsu/KVS.git
cd KVS/builder/
```

2) Make sure you have the following dependicies installed: <br />
```
gdisk e2fsprogs
```

3) Run the builder: <br />
```
sudo bash builder.sh <path to RAW shim> <optional flags>
```


## Booting a KVS shim
After flashing KVS to a RAW shim, download & open the [Chrome Recovery Utility](https://chromewebstore.google.com/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm?pli=1). <br />
![image](https://github.com/kxtzownsu/KVS/assets/116377025/d30f383e-73c2-4809-a025-850490679dc9)
<br />
Press the Settings (⚙️) icon in the top right, and press "Use Local Image". Select your built KVS shim, and then select your target USB / SD.

After it is done flashing, go to your target chromebook, press 
