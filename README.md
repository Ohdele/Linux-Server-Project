## Core Component Verification
### Objective: Verify system boot state and installed kernel components.
**Commands Executed:**
1. `ls /boot` (To inspect kernel and bootloader files)
2. `uname -r` (To confirm the active kernel version)
**Analysis:** The system has multiple kernels installed (e.g., 6.8.0-40 and 6.8.0-87), confirming a robust boot configuration. The active kernel is 6.8.0-87-generic. **[View Output in task1-boot-info.txt]**

## Storage Design and Implementation (LVM)
### Objective: Implement Logical Volume Management (LVM) for flexible storage partitioning.
### Steps and Analysis:
1. **Disk Identification (`lsblk`):** Identified the dedicated 5GB disk (`/dev/sdb`) as available for storage integration.
2. **LVM Creation:** Used `pvcreate`, `vgcreate (vg_data)`, and `lvcreate (lv_apps)` to pool the entire 5GB disk space into a single logical volume.
3. **Filesystem and Mount:** Formatted the Logical Volume with `ext4` and mounted it to the dedicated service path `/srv/appdata`.
4. **Verification (`df -h`):** Confirmed the LVM device (`/dev/mapper/vg_data-lv_apps`) is successfully mounted and ready for application data.
**[View Output in task2-storage-setup.txt]**
## User and Group Management
### Objective: Configure dedicated users and groups with appropriate access controls.
1. **Group and User Creation:** Created the `app_team` group and the dedicated system user `app_user` (`-g app_team`).
2. **Security and Ownership:** Set the ownership of the LVM mount point (`/srv/appdata`) to `app_user:app_team` and applied restrictive permissions (`chmod 770`).
3. **Verification:** Confirmed only the owner and group have read/write/execute permissions: `drwxrwx---`. **[View Output in task3-user-mgmt.txt]**
