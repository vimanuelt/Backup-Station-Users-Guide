# **Backup Station Users Guide**

Backup Station is a graphical application for managing ZFS Boot Environments (BEs) on GhostBSD. It allows you to easily create, rename, activate, and manage boot environments through an intuitive GUI. 

---

## **Features**

- **Create** new boot environments to safeguard your system before changes.
- **Rename** existing boot environments for better organization.
- **Activate** a boot environment and switch to it on the next reboot.
- **Delete** unused boot environments to free up disk space.
- **Mount and Unmount** boot environments for file recovery or inspection.

---

## **Installation**

### **Prerequisites**
Ensure the following are installed on your system:
- Python 3
- ZFS utilities (`zfs-utils` or equivalent)

### **Steps to Install**
1. Clone the Backup Station repository:
   ```bash
   git clone https://github.com/ghostbsd/backup-station.git
   ```
2. Navigate to the cloned directory:
   ```bash
   cd backup-station
   ```
3. Run the setup script with root privileges:
   ```bash
   sudo python3 setup.py install
   ```

Backup Station should now be installed and ready to use.

---

## **Getting Started**

1. Open the application menu and launch **Backup Station**.
2. Enter your administrator password if prompted.
3. The main window will display a list of your existing boot environments.

### **Main Window Overview**

| Column          | Description                                      |
|------------------|--------------------------------------------------|
| **BE Name**      | Name of the boot environment.                    |
| **Active**       | Indicates whether the boot environment is active.|
| **Mountpoint**   | Mount location of the boot environment.          |
| **Space**        | Disk space used by the boot environment.         |
| **Date**         | Creation date of the boot environment.           |
| **Time**         | Creation time of the boot environment.           |

At the bottom of the window, you’ll find buttons for managing boot environments.

---

## **Step-by-Step Guide**

### **Create a New Boot Environment**
1. Click the **Create BE** button.
2. Enter a name for the new boot environment (e.g., `BeforeUpdate` or `TestEnv`).
3. Click **OK** to confirm. The new boot environment will appear in the list.

### **Rename a Boot Environment**
1. Select a boot environment by clicking its name.
2. Click the **Rename BE** button.
3. Enter the new name and click **OK**. The list will update with the new name.

### **Activate a Boot Environment**
1. Highlight the boot environment you want to activate.
2. Click the **Activate BE** button.
3. Reboot your system to switch to the selected environment.

### **Delete a Boot Environment**
1. Select the environment you want to delete.  
   - **Note:** You cannot delete the active environment. Switch to another one first.
2. Click the **Delete BE** button.
3. Confirm the deletion. The boot environment will be removed.

### **Mount a Boot Environment**
1. Select the desired boot environment.
2. Click the **Mount BE** button. The mount point will appear in the **Mountpoint** column.

### **Unmount a Boot Environment**
1. Select the mounted boot environment.
2. Click the **Unmount BE** button. The mount point will disappear.

---

## **Pro Tips for Efficient Management**

1. **Use Descriptive Names**  
   Name your boot environments based on their purpose (e.g., `BeforeUpgrade`, `StableSetup`, or `ExperimentEnv`) to stay organized.

2. **Backup Before Changes**  
   Always create a boot environment before system updates, software installations, or major configuration changes.

3. **Clean Up Regularly**  
   Delete old or unused environments to free up disk space and keep the list manageable.

4. **Monitor Disk Usage**  
   Use the **Space** column to track how much space each environment uses. Enable ZFS compression to save space.

5. **Test Safely**  
   Create separate boot environments for testing new software or configurations. This way, your stable environment stays untouched.

6. **Document Changes**  
   Maintain a simple log of what each environment contains and the changes made to it for quick reference.

7. **Inspect with Mount**  
   Use the **Mount** feature to access or troubleshoot files in a boot environment without activating it.

8. **Enable Snapshots**  
   Consider using ZFS snapshots alongside Backup Station for an additional layer of data safety.

9. **Don’t Overdo It**  
   Avoid clutter by limiting boot environments to key milestones or checkpoints.

---

## **Troubleshooting**

### **Backup Station Won’t Open**
If the app doesn’t launch, try starting it from the terminal:
```bash
sudo backup-station
```
This will display any error messages.

### **Password Issues**
Ensure you’re entering the correct administrator password. Backup Station requires elevated permissions to manage boot environments.

### **Need Help?**
Visit the [GitHub repository](https://github.com/ghostbsd/backup-station) to report bugs or seek support.

