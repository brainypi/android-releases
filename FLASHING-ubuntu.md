Guide for Flashing to eMMC on Linux Host
1. Hardware Requirements
1. BrainyPi/Brainy Pro v1.0
2. Laptop/PC
3. USB 5V 3A Power Supply 
  

4. USB Type C cable 
  

5. USB Male A to Male A cable
  

6. USB to TTL Serial Cable (Optional)
  

2. Installing Tools and Drivers
2.1 Source Folder
Source folder should contain files and folders as given below
.
├── brainypi-recovery.img
├── brainypi-recovery.img.info
├── FlashingGuide-Windows.pdf
├── FlashingGuide-Linux.pdf
├── md5sum.md5
├── ReleaseNotes.md
├── rk3399_loader_v1.20.119.bin
└── tools
   ├── Linux
   │   └── rkdeveloptool-v1.32.zip
   └── Windows
       ├── DriverAssitant_v5.0.zip
       └── RKDevTool_Release_v2.81.zip
2.2 Steps to Install tools


1. Navigate to tools —-> Linux folder.
2. Extract the file rkdeveloptool-v1.32.zip
3. Navigate to folder rkdeveloptool and Open a new Terminal in the folder. 
4. Run these commands given below to compile and Install rkdeveloptool 
  

5. Check if the tool was installed successfully. 
  











3. Boot into MaskRom mode
1. Power off the board.
2. Remove microSD card (if inserted before). 
3. Connect USB Male A to Male A cable to Board’s Top USB 3.0 slot and to Laptop/PC.  
4. Press and hold the Maskrom key on the backside of the Board. 
  



   5. Power on the board. 
   6. Release the Maskrom key. (Important to release the key)
   7. Confirm that your board is in Maskrom mode by running the lsusb command  
You should see “RK3399 in Mask ROM mode” message in the output




4. Flash into eMMC
      1. On your Laptop/PC, Open new Terminal
      2. Run the command rkdeveloptool ld it should show the board connected
  

      3. Download the loader into eMMC by running the command
rkdeveloptool db rk3399_loader_v1.20.119.bin
      4. Download the GPT image to eMMC, by running the command 
rkdeveloptool wl 0 brainypi-recovery.img
      5. Reboot the device by running the command 
rkdeveloptool rd
      6. Now the device should boot the new image on eMMC.
