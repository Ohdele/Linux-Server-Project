## Core Component Verification
### Objective: Verify system boot state and installed kernel components.
**Commands Executed:**
1. `ls /boot` (To inspect kernel and bootloader files)
2. `uname -r` (To confirm the active kernel version)
**Analysis:** The system has multiple kernels installed (e.g., 6.8.0-40 and 6.8.0-87), confirming a robust boot configuration. The active kernel is 6.8.0-87-generic. **[View Output in task1-boot-info.txt]**

## Storage Design and Implementation (LVM)
### Objective: Implement Logical Volume Management (LVM) for flexible storage partitioning.
