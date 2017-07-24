# Module 2: Building Application Infrastructure in Azure

# Lab: Creating an Azure Virtual Machine for Development and Testing

### Exercise 1:	Creating a Network and Resource Container

#### Task 1: Sign in to the Azure Portal

1. On the Start screen, click the **Internet Explorer** tile.

2. Go to <https://portal.azure.com>

3. Enter the email address of your Microsoft account. Click **Continue**.

4. Enter the password for your Microsoft account.

5. Click **Sign In**.

#### Task 2: Create a Resource Group

1.  In the navigation pane on the left side of the Azure Portal, scroll down, and then click **More Services**.

2. In the **Browse** blade that displays, click **Resource groups**.

3. In the **Resource groups** blade that displays, view your list of resource groups.

4. At the top of the **Resource groups** blade, click the **Add** button.

5. In the **Resource group** blade, perform the following steps:

  a. In the **Resource group name** dialog box, provide the value **20532**.

  b. In the **Resource group location** list, select the region that is closest to your current location.

6. In the **Resource group** blade, click **Create**.

#### Task 3: Create a Virtual Network

1.  In the navigation pane on the left side of the Azure Portal, scroll down, and then click **More Services**.

2. In the **Browse** blade that displays, click **Virtual networks**.

3. In the **Virtual networks** blade that displays, view your list of virtual network instances.

4. At the top of the **Virtual networks** blade, click the **Add** button.

5. In the **Create virtual network** blade, perform the following steps:

  a. In the **Name** dialog box, provide the value **vnet20532**.

  b. In the **Location** list, select the region that is closest to your current location.

  c. Ensure that the **Address space** box has the value **10.0.0.0/16**.

  d. In the **Subnet name** box, provide the value **Apps**.

  e. Ensure that the **Subnet address range** box has the value **10.0.0.0/24**.

  f. In the **Resource group** section, select the **Use existing** option.

  g. In the **Resource group** section, locate the dialog box and provide the value **20532**.

6. In the **Create virtual network** blade, click **Create**.

> **Results:** After completing this exercise, you will have a new virtual network and resource group in Azure

### Exercise 2:	Creating a Development Virtual Machine

#### Task 1: Create a storage account

1.  In the navigation pane on the left side of the Azure Portal, scroll down, and click **More Services**.

2. In the **Browse** blade that displays, click **Storage Accounts**.

3. In the **Storage accounts** blade that displays, view your list of Storage instances.

4. At the top of the **Storage accounts** blade, click the **Add** button.

5. In the **Create storage account** blade that displays, perform the following steps:

  a. In the **Name** box, provide the value **stor20532[your name in lowercase here]**.

  b. In the **Deployment model** section, ensure that the *Resource manager* option is selected.

  c. In the **Account kind** list, ensure that the *General purpose* option is selected.

  d. In the **Performance** section, ensure that the *Standard* option is selected.

  e. Click on the **Replication** list and select the **Locally-redundant storage (LRS)** option.

  f. In the **Storage service encryption** section, ensure that the *Disabled* option is selected.

  g. In the **Resource group** section, select the **Use existing** option.

  h. In the **Resource group** section, locate the dialog box and provide the value **20532**.

  i. In the **Location** list, select the region closest to your current location.

  j. Ensure that the **Pin to Dashboard** option is selected.

  k. Click **Create**.

    > **Note** Wait for Azure to finish creating the storage account prior to moving forward with the lab. You will receive a notification when the *Storage Account* is created and you will see the Storage Account's blade.

#### Task 2: Create a virtual machine

1. In the navigation pane on the left side of the Azure Portal, scroll down, and click **More Services**.

2. In the **Browse** blade that displays, click **Virtual machines**.

3. In the **Virtual machines** blade that displays, view your list of Virtual Machine instances.

4. At the top of the **Virtual machines** blade, click the **Add** button.

5. In the **Virtual Machines** blade that displays, search for and select the following template:

  - Visual Studio Community 2017 on Windows Server 2016 (x64)

  > **Note:** Ensure that you select this specific template as all further lab instructions assume that you are using this exact Azure SDK version, OS and Visual Studio version.

6. In the **Visual Studio Community 2017 on Windows Server 2016 (x64)** blade, ensure that the **Resource Manager** deployment model is selected and click the **Create** button.

6. In the **Create virtual machine** blade that displays, click **Basics** and perform the following steps:

  a. In the **Name** dialog box, provide the value **vm20532**.

  b. In the **VM disk type** list, select the value **HDD**.

  c. In the **User Name** dialog box, provide the value **Student**.

  d. In the **Password** and **Confirm Password** dialog boxes, provide the value **AzurePa$$w0rd**

  e. In the **Subscription** section, select the subscription you wish to use.

  f. In the **Resource Group** section, locate the **Use existing** option, and then select the **20532** resource group.

  g. In the **Location** list, select the region closest to your current location.

  h. Click **OK**.

7. In the **Create Virtual Machine** blade that displays, click **Size** and perform the following steps:

  a. Locate and click the **View all** hyperlink.

  b. Locate and select the **F4 Standard** option.

  c. Click the **Select** button.

8. In the **Create Virtual Machine** blade that displays, click **Settings** and perform the following steps:

  a. Under the **Storage > Use managed disks** section, select the **No** option.

  b. Click the **Storage Account** section and then select **stor20532[your name here]**.

  c. Click the **Virtual Network** section and then select **vnet20532**.

  d. Click the **Subnet** section and then select **Apps**.

  e  Leave default values for **Public IP Address**, **Network Security Group (firewall)**, **Extensions** and **High Availability**.

  f. Under the **Monitoring > Boot diagnostics** section, select the **Disabled** option.
 
  g. Under the **Monitoring > Guest OS diagnostics** section, select the **Disabled** option.

  h. Scroll down and click **OK**.

9. In the **Create Virtual Machine** blade that displays, click **Summary** and click **OK** to create the virtual machine using your specified configuration.

  > **Note:** The creation of a new virtual machine can take anywhere between 10 to 15 minutes. You will see a notification on the Dashboard (home screen) when your virtual machine is created and running.

10. Select the newly created virtual machine from your Dashboard.

11. In the **vm20532** blade, locate the **Settings** section.

12. In the **Settings** section, select the **Disks** option.

13. In the **Disks** blade, click **Add data disk**.

14. In the **Attach a new disk** blade, perform the following steps:

  a. In the **name** box, provide **vm20532-AllFiles**
  
  b. For **Source type**, select **New (empty disk)**
  
  c. For **Account type**, select **Standard (HDD)**.

  c. In the **Size (GiB)** dialog box, provide the value, **128**.

  d. In the **Storage container** section, click on **Browse** and then from the **Storage account** blade, select the previously created storage account, **stor20532[Your Name Here]**

  e. In the **Containers** blade, select **vhds** container and click **Select**.

  f. To create the second disk, click **Save**.

  > **Note:** Wait about five minutes for the empty disk to be attached to the virtual machine.

15. Select the **Overview** option to return to the **vm20532** blade.

16. Click **Connect** at the top of the screen.

17. In the **Internet Explorer download** dialog box, click **Open**.

18. In the **Remote Desktop Connection** dialog box, perform the following steps:

  a. Click **Don�t ask me again for connections to this computer** to prevent this dialog box from displaying again.

  b. Click **Connect**.

19. In the **Windows Security** dialog box, perform the following steps:

  a. For the **User name** dialog box, provide the value, **Student**.

  > **Note:** If you computer is on a domain, you may need to add a backslash before the username to "escape" the domain.

  b. For the **Password** dialog box, provide the value, **AzurePa$$w0rd**.

  c. Click **OK**.

10. In the **Remote Desktop Connection** dialog box, perform the following steps:

  a. Verify if the Remote certificate name matches the name of your virtual machine.

  b. Click **Don�t ask me again for connections to this computer** to prevent this dialog box from displaying again.

  c. Click **Yes**.

11. When you are prompted to allow your network connection to discover external devices, click **Yes**.

> **Results:** After completing this exercise, you will have a new virtual machine stored in a new storage account.

### Exercise 3: Configuring the Virtual Machine for Development

#### Task 1: Disable IE Enhanced Security Configuration

1.  On the Start screen, click the **Server Manager** tile.

2. In the navigation pane on the left side, click **Local Server**.

3. In the **Properties** box, click the **IE Enhanced Security Configuration** option that is currently set to **On**.

4. In the **Internet Explorer Enhanced Security Configuration** dialog box, perform the following steps:

  a. Under *Administrators*, select **Off**.

  b. Under *Users*, select **Off**.

  c. Click **OK**.

#### Task 2: Create an AllFiles Drive

5. Press the ``Windows logo key + W`` to open **Universal Search � Settings**.

6. In the **Search** dialog box, provide the value **disk**.

7. Click **Create and format hard disk partitions**.

8. In the **Initialize Disk** dialog box, perform the following steps:

  a. Verify that **Disk 2** is selected for initialization.

  b. Verify that **MBR (Master Boot Record)** is the selected partition style.

  c. Click **OK**.

9. In the lower-half of the Disk Management window, perform the following steps:

  a. Scroll down and find **Disk 2** that was previously initialized.

  b. Right-click the unallocated partition, and then click **New Simple Volume**.

10. In the **New Simple Volume** wizard, perform the following steps:

  a. Click **Next**.

  b. Verify that the **Simple volume size in MB** is a number greater than **100000**.

  c. Click **Next**.

  d. In the **Assign the following drive letter** list, click **F**.

  e. Click **Next**.

  f. Verify that the **File System** setting is set to **NTFS**.

  g. In the **Volume Label** dialog box, provide the value **AllFiles**.

  h. Click **Next**.

  i. Click **Finish** to close the dialog box, and then create the partition.

  > **Note:** If a dialog box displays stating that �You need to format the disk in drive F: before you can use it.�, you can safely close it because you already formatted the disk.

#### Task 3: Download the AllFiles Content

11. On the Start screen, click the **Internet Explorer** tile.

12. If you are prompted to set up Internet Explorer 11, perform the following steps:

  a. Select **Use recommended security, privacy and compatibility settings**.

  b. Click **OK**.

13. Go to (https://github.com/MicrosoftLearning/20532-DevelopingMicrosoftAzureSolutions/releases/latest).

14. Scroll down the screen until you find the **allfiles** download link.

15. Click the link to download the AllFiles compressed folder.

16. In the **Internet Explorer** download dialog box, click **Save**.

  > **Note:** The download of the AllFiles executable typically takes around five minutes.

17. Click the **Windows File Explorer** icon in your Taskbar.

18. On the left navigation bar, expand the **This PC** node and click the **Downloads** node:

19. Right-click the **allfiles** compressed folder and select the **Properties** option.

20. In the **allfiles Properties** dialog box, do the following:

  a. Click **Unblock** if present.

  b. Click **OK**.

21. Right-click the **allfiles** compressed folder and select the **Extract all** option.

22. In the **Extract Compressed (Zipped) Folders** dialog box, do the following:

  a. In the **Files will be extracted to this folder:** dialog, provide the value **F:\\**.

  b. Ensure that the **Show extracted files when complete** checkbox is not selected.

  c. Click **Extract**.

23. Wait for the extraction process to complete.

#### Task 4: Add your Azure subscription to Visual Studio

1. On the Start screen, locate and click the **Visual Studio 2017** tile.

  > **Note:** You might have to use the down arrow to locate the Visual Studio 2017 tile on your Start screen.

2. You will be prompted to sign-in using a **Microsoft Account**. Perform the following steps:

    a. Click the **Sign in** button.

    b. Enter the email address of your Microsoft account. Click **Continue**.

    c. Ensure that the **Keep me signed in** option is selected.

    d. Enter the password for your Microsoft account.

    e. Click **Sign In**.

    > **Note:** You may be prompted by Internet Explorer to remember this password. You can safely close and ignore this dialog.

3. If you have never used **Visual Studio** in the past, you will be prompted to configure your Microsoft Account. Perform the following steps:

    a.  Select your **country\region** from the provided list.

    b.  Leave the remaining fields set to their default values.

    c.  Click the **Continue** button.

3. If you have never used **Visual Studio** in the past, you will also be prompted to configure the apperance of your IDE. Perform the following steps:

    a.  Leave all fields set to their default values.

    b.  click the **Start Visual Studio** button.

4. Wait for *Visual Studio* to finish **preparing for first use**.

    > **Note:** This process typically takes between 2 to 5 minutes.

4. Validate that you can see the Visual Studio **Start Page**.

> **Results:** After completing this exercise, your development virtual machine will have your lab files installed. Your virtual machine will also have Visual Studio, Azure PowerShell, and the Azure SDK installed.


#### Task 5: View, stop, start and delete resources associated with a virtual machine

1. Stop the virtual machine. 

   > **Note:**You will only complete step 1 in task 5 until the end of the course. The virtual machine will be used to complete the remaining labs.
	
	a. Select all resources

	b. Select the virtual machine named vm20532

	c. Select stop to stop the instance

	d. Select start, then connect to restart the virtual machine

2. Delete the virtual machine

	a. Select all resources

	b. Select the virtual machine named vm20532.

	c. Select Delete to permanently remove the VM instance

3. Delete the virtual network

	a.  Select all resources

   	b.  Select vnet20532

	c.  Select delete to permanently remove the virtual network
	

4. Delete the storage account

	a.  Select all resources

   	b.  Select stor20532[yourname]

	c.  Select delete to permanently remove the stoarge account

