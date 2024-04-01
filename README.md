# ⚠️ Disclaimer

**I am not responsible for what you do with your device**. If you try to do anything that is written in this repo and mess up, **you take full responsability**. However if you want to use your banking apps on a rooted device, I suggest you first **make a backup**.

# 🍁 Swedbank-OEM-Bypass

Swedbank's Android application checks if you have your bootloader unlocked and if you do, they will not allow you to make NFC payments/create a digital card. This is a huge problem if you want to use NFC payments on a custom rom/rooted device.

Note 0: this method only bypassed the bootloader unlocked check, you may need to take some additional steps to get the app to work.

Note 1: if you are using other bank application and it checks for unlocked bootloader, this will probably work, I only tested it on Swedbank's app though.

# 📚 Prerequisites

* Unlocked bootloader
* Root
* Termux(or some kind of other terminal app)
* KernelSU(if you are using Magisk, find a way to hide it youself)
* Custom rom(optional)
* SafetyNet pass(you fix SafetyNet pass using a module)
* Swedbank's application and account

# 🎇 Bypass

1. Clear storage and cache of Swedbank's app
2. Grant root permissions to Termux
3. Check the status of your bootloader

`getprop sys.oem_unlock_allowed`

0 - locked
1 - unlocked

4. If it says 1 launch the following command

`su -c 'setprop sys.oem_unlock_allowed 0'`

Note: This is not persistent. If you want the app to work after reboot find a way to run this command on boot. I think you could use something like tasker for this.

5. Open the Swedbank app
6. Log in
7. You should now be able to make NFC payments

# 📜 License

This project is licensed under the GPL v2 [LICENSE](LICENSE).
