# Model O Firmware Update Workaround
Tutorial work around for Glorious Model O Wireless (Probably works for the Model O Wired as well)
-------------------------------------------------------------------------------------------------
**Disclaimer:** If you brick your mouse, I'm not responsible. This might work for the wired model O as well. I imagine the wired only has to update a single firmware, where as the wireless has to update two (the mouse itself and the wireless portion of the mouse).

--------------------------------------------------------------------------

Having issues updating your firmware for your Model O Wireless? Tried all the suggestions like, running glorious core as admin, resetting the firmware, unplugging, replugging, disabling your AV, etc and it still not working?

Are you still running into this?

![Installing Firmware 0%](https://i.imgur.com/4I4ymfo.png)

![Firmware Update Failed](https://i.imgur.com/6WRMV1E.png)

-------------------------------------------------------------------------
Then do the following:

1. Backup any configuration/lighting/binding profiles in Glorious Core (export profiles), especially if you have a GMMK Pro like I do.    

2. Exit Glorious Core.   

3. Download and install 7-zip (you can use WinRar).    
https://www.7-zip.org/download.html

4. Press the Windows key + R on your keyboard and then type in **%appdata%** and hit enter.    
![](https://i.imgur.com/zAe2oIg.png)

5. Double-click on the **Glorious Core** folder.    
![](https://i.imgur.com/8KFW9u9.png)

6. Double-click on the **data** folder.    
![](https://i.imgur.com/F3EhuHn.png)

7. These two files are important.    
![](https://i.imgur.com/WxdSh9x.png)

8. Right-click one of them, and then go to the 7-zip menu, and choose “Extract to “v3.0.8_Model_OFirmware….”
![](https://i.imgur.com/HLXeYhq.png)

9. Do the same for the other firmware .exe file.

10. You should now have two folders with an exe and zip file of the same names in each.  
**v3.0.8_Model_OFirmware** is the firmware for the mouse itself.     
**v3.0.8_Model_OFirmwareWireless** is the firmware for the wireless dongle/wireless receiver in the mouse.    
![](https://i.imgur.com/dTcewnp.png)

11. Open the first folder and drag and drop the `XVI.zip` file to your desktop.  

12. Right-click the Zip file and choose 7zip->`Extract to "XVI\"` - The password is `XVI`  

13. Open this new folder and create a new folder within it named `NRF52840` and another folder named `NRF52810+264J` (these are the correct names).  

14. Now move the 3 .hex files into the `NRF52840` folder  

    **So for `v3.0.8_Model_OFirmware\NRF52840`**  
        ```CM2822_Mouse_USB_v0.03.08_20210112.hex```  
        ```DX_264_Dongle_v0.03.09.05_20200521.hex```  
        ```DX_Receiver_810_v0.03.09_20200521.hex```  

    **and for `v3.0.8_Model_OFirmwareWireless\NRF52840`**  
        ```CD_264_Dongle_v0.01.03_20200629.hex```  
        ```CD_Receiver_APP_v0.01.03_20200629.hex```  
        ```CM2822_Receiver_USB_v0.03.08_20210112.hex```  


15. You don't put anything into the `NRF52810+264J` folder. It remains empty.  

16. It should look like this in the XVI folder.  
![](https://i.imgur.com/LkhUth7.png)
![](https://i.imgur.com/3sXgZSV.png)

17. Now drag and drop those files back into the folder where you had moved the .zip file out from.  
![](https://i.imgur.com/6Gag0qm.png)

18. It should look like this:  
![](https://i.imgur.com/YPo7c7k.png)

19. Now open the FirmwareUpdate.exe (do not need to do it as admin).  

20. It should hopefully open the FirmwareUpdate.exe as normal. If you see it, just move on to step 21. 

	20b. If you don't see the window, see if you can find it in task manager and bring it to front.  In the “**Processes**” tab you should see “**FirmwareUpdate (32 bit)**” listed, expand it and then right-click on its sub-process “**FirmwareUpdater**” and choose “Bring to Front.”
	![](https://i.imgur.com/RSjgrmV.png)

21. You should see a window similar to this (make sure ATE is **UNCHECKED**).  
![](https://i.imgur.com/Jkc5NdT.png)

**(If FirmwareUpdate.exe automatically closes then there is some kind of AV software that may be closing it. If you can't find a solution to that at this time then your best bet is to make a Win7, Win8, or Win10 VM in something like Virtualbox. Mount the mouse and the wireless dongle into the VM, install glorious core and try all these steps over again.)**

22. You'll see a window like this (don't worry if you don't see/read the same version numbers as my screenshot. Uncheck the ATE box and then click on Update and wait. The program may "freeze" at the end, continue to wait. Your mouse might stop responding as well. Just wait.    
![](https://i.imgur.com/Jkc5NdT.png)
![](https://i.imgur.com/PotsPIU.png)

23. It might sit on a "Verify OK" message, keep waiting until you see "PASS".    
![](https://i.imgur.com/ZyjkZ1G.png)

24. Cool, the mouse firmware just updated. Now close this program out, go to the other firmware folder that you extracted and repeat the steps from step 10/11 and onward (overwrite the first XVI.zip file with the next one you work with or move or rename the first XVI.zip file which is what I did. I kept one named as `XVI.zip` and the renamed the other to `XVI.wireless.zip`). You have to do both for the wireless model O because it updates firmware for the mouse and for the wireless dongle.

25. Once you've updated both firmware, you can reopen glorious core. If glorious core loads blank (after waiting a minute or two, just uninstall and reinstall it. Import the profiles you exported at the start of this tutorial.
