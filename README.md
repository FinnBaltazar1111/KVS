# KVS
KVS: Kernel Version Switcher, made to easily switch the `tpm_kernver` on Chromebooks.


## Prerequisites
* Target Chromebook *must* be unenrolled, and FWMP *must* also be disabled
* External storage to flash shim (preferrably a USB)
* The ability to build a shim (prebuilt shims are hosted [here](https://dl.darkn.bio/KVS)


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
After flashing KVS to a RAW shim, download & open the [Chromebook Recovery Utility](https://chromewebstore.google.com/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm). <br />
![image](https://kxtz.dev/reco-util.png)
<br />
Press the Settings (⚙️) icon in the top right, and press "Use Local Image". Select your built KVS shim, and then select your USB/SD.

After it is done flashing, go to your target Chromebook and go to the recovery screen (<kbd>**ESC**</kbd><kbd>**REFRESH**</kbd><kbd>**POWER**</kbd>). Press <kbd>**CTRL**</kbd><kbd>**D**</kbd>, then <kbd>**ENTER**</kbd> to boot into devmode. Then plug in the KVS drive and press <kbd>**ESC**</kbd><kbd>**REFRESH**</kbd><kbd>**POWER**</kbd> to boot the shim.

## Usage
(for ultra-skidiots)

Once KVS has fully booted, you should see this:
```
KVS: Kernel Version Switcher v1
Current kernver: <your kernver>
TPM Version: 2.0
TPMD: trunksd
-=-=-=-=-=-=-=-=-=-=-
1) Set New kernver
2) Backup kernver
3) Bash shell
4) Credits
5) Exit
> 
```

You're probably here just to switch your kernver, so type `1`. You should see: `Please Enter Target kernver (0-4)` or `Please Enter Target kernver (0-3)`. Enter the kernver you want, then click <kbd>**ENTER**</kbd>. If it works, great! If not, you probably neglected to read the sixth line in this README.
