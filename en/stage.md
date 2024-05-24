# Scene image

1. Take the previous [image](hotel.md)
2. Create another user - name **Admin** password **"your_password"** with administrator rights.
3. Disabling browsers **Chrome/Internet Explorer/Edge** - open the location **Chrome** "C:\Program Files\Google" in the folder properties, select **Security/Edit**, select **Users** and click **Remove**. Do the same actions with **Edge** "C:\Windows\SystemApps" folder **Microsoft.MicrosoftEdge_8wekyb3d8bbwe.** In order to disable **Internet Explorer** - you need to go to **"Programs and Features"** in the control panel and in the **"Turn Windows features on or off"** tab, uncheck **Internet Explorer 11.**
4. Disable the USB ports, press **Win+R**, write **gpedit.msc** and go to **Local Computer Policy > Computer Configuration > Administrative Templates > System > Removable Storage Access** and enable the deny rule **Deny all access**
5. To disable on **powershell.exe**, you need to go to **"Programs and Features"** in the control panel and in the **"Turn Windows features on or off"** tab uncheck **Windows PowerShell 2.0**. To disable **cmd.exe** write **gpedit.msc**, go to **User Configuration > Administrative Templates > System** and select **Prohibit command line use**, check the **Enabled** checkbox and in the parameters select **Yes**, then in **Win+R** write the command **gpupdate /force** to update the policy
6. For the visual, delete the folders **Download, Picture, Video** and others from **My Computer**:
Press **Win+R**, write **regedit.msc**, go to **HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Explorer > FolderDescriptions**, and look for the folders we need:
```sh

Desktop: {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}
Documents: {f42ee2d3-909f-4907-8871-4c22fc0bf756}
Downloads: {7d83ee9b-2244-4e70-b1f5-5393042af1e4}
Music: {a0c69a99-21c8-4671-8703-7934162fcf1d}
Pictures: {0ddd015d-b06c-45d5-8c4c-f59713854639}
Videos: {35286a68-3c57-41a1-bbb1-0eae73d76c95}
3d_Objects: {31C0DD25-9439-4F12-BF41-7FF4EDA38722}
```
Open the **PropertyBag** folder, and change the **ThisPCPolicy** value from **Show** to **Hide**

7. Return to the IT folder on drive C and create the Software folder. Download programs for [SteelSeries Engine](https://steelseries.com/gg/engine) / Razer Synapse [2](https://www.razer.com/synapse-2) + [3](https://www.razer.com/synapse-3) / [Corsair](https://www.corsair.com/s/icue) / [Logitech](https://www.logitechg.com/en-eu/innovation/g-hub.html) / [HyperX](https://row.hyperx.com/ru/pages/ngenuity). The same goes for [FocusRite](https://downloads.focusrite.com/focusrite/scarlett-3rd-gen/scarlett-2i2-3rd-gen) which we install right away.
8. Go to **Admin**, change the account for the player making it without administrator rights, then go to it, check that you cannot use one of the above browsers. Checking **Steam** + launching the game (After checking, exit **Steam** by changing the user so that the login field is empty). Testing **TeamSpeak 3** and **ASIO (Focusrite).**
9. Well, that’s all, we save it in **Acronis True Image**, the name is the same as for the hotel but without the signature **"Hotel"**.


## Individually on each PC on stage
1. Set a password on **BIOS**
2. Enable the **XPM-I** profile, press **F7**, go to the **Ai Tweaker** tab and select **Ai Overclock Tuner**
2. Enable Secure Boot, set **UEFI** to boot only, remove all boot devices except the OS drive (specifically make sure USB booting is not possible), and enable **VT-d (Virtualization)** if the hardware supports it.


## Required items on the Major Stage
1. When creating an image, your **Steam** account must have access to **PerfectWorld**
2. Add cards from the **Workshop**
3. Add the **USRLOCALCSGO** variable for the **C:\configs** folder
4. Setting up **disk auditing** to view all changes on the disk, press **Win+R**, write **secpol.msc**, go to **Security Settings > Local Policies > Audit Policy** select **Audit object access**, put two checkboxes on **Success** and **Failure**. Next, on the disk, right-click **Properties > Security > Advanced > Auditing**, click **Add**, select **Principal** and add the **Everyone** object, after adding, select all permissions and save everything. `To view the logs, go to Win+R > compmgmt.msc > Event Viewer > Windows Logs > Security `
5. Set the player machines to use local host **(127.0.0.1)** for **DNS**, otherwise players will experience stalls while trying to reach an external **DNS** due to the network restrictions.