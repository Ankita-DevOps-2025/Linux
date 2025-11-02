FLOW

Power On
   ↓
BIOS/UEFI (Hardware check)
   ↓
GRUB Bootloader
   ↓
Linux Kernel Loads
   ↓
initramfs Loads Drivers
   ↓
Kernel mounts root filesystem
   ↓
Systemd (PID 1) starts
   ↓
All system services start
   ↓
Display Manager / TTY / SSH starts
   ↓
Login Interface appears
   ↓
User authentication via PAM
   ↓
User shell loads
   ↓
You get terminal or GUI desktop



# Linux BOOT PROCESS Explained (UEFI, GRUB, Kernel & systemd)
BIOS (Basic Input output System)/UEFI(unified extensible firmware interface)
MBR (Master Boot Record)/ESP
GRUB (Grand Unified Boot Loader)
Kernel
SYSTEMD/INIT

1. CPU Initialization
At system start or reset...The CPU is hard-wired to start executing instructions from a fixed address (called the reset vector) which maps to firmware stored in non-volatile memory (like ROM or Flash memory) which is called BIOS or UEFI firmware.

2. BIOS (Basic Input output System)/UEFI(unified extensible firmware interface)
Both are firmware & first program stored on the motherboard.
Who stores the the firmware BIOS/UEFI in motherboard?
Motherboard or Server vendors/manufactuer are responsible for doing it.

- POST (Power-On Self-Test) $\rightarrow$ Both check and initialize hardware components (CPU, RAM, storage, peripherals).
- Once POST passes, the BIOS/UEFI firmware looks for a bootable device (like SSD, HDD, Pendrive or network)
- Once bootable device found then...

BIOS -> MBR | UEFI -> ESP

# Master Boot Record (MBR):
Master Boot Record
It is the first sector of any bootable device of 512 Bytes. * The MBR contains machine code instructions that help boot the machine.

MBR includes the following structure:
- Bootloader code: 446 bytes — a small program that acts as the first-stage bootloader, responsible for loading the second-stage bootloader (such as GRUB).
- Partition table: 64 bytes — partition table tells the bootloader and OS where the partitions are located on the disk.
- Boot signature: 2 bytes — serves as a marker to indicate that the sector contains a valid MBR.

# EFI System Partition (ESP)
- EFI System Partition
- It is a special partition on a GPT-formatted disk used by UEFI firmware.
- Typical size: 100–500 MB
- UEFI directly loads an .efi executable (e.g., bootx64.efi or grubx64.efi).

# GRUB2
- GRUB2 is the modern, modular, UEFI-compatible version of GRUB with better filesystem support, scripting, and graphical features.
- First it will read its config
    /boot/grub2/grub.cfg (BIOS)
    /boot/efi/EFI/<distro>/grub.cfg (UEFI)
- The user sees a text-based or graphical menu listing the OSes/kernels configured to boot.
- Select kernel:
- Once a kernel is selected (manually or automatically via default), GRUB2 locates the kernel binary and initrd/initramfs image, and loads both in RAM:
    /boot/vmlinuz-<kernel-version>
    /boot/initramfs-<kernel-version>.img
- After this it passes control to linux kernel which continues the boot process.

- Initramfs (Initial RAM File System) is a small, temporary filesystem loaded into your computer's RAM 🧠 during startup.
- It contains the essential drivers and tools the Linux kernel needs to find and mount your main, permanent filesystem (the one on your hard drive or SSD 💽).
- Once the real filesystem is running, the initramfs is cleared from memory, having completed its mission

# Kernal
The Linux kernel is the core program of the operating system that controls all the computer's hardware and allows software to run.

- Linux kernel loaded in memory by GRUB.
- At this stage, the kernel itself is decompressed.
- The initramfs (or older initrd) is a temporary root filesystem loaded into RAM.
- It contains essential drivers, modules, and scripts needed to mount the real root filesystem (e.g., LVM, RAID, encrypted partitions).
- The initramfs detects hardware and loads required modules from its temporary filesystem.
- Once all required drivers are loaded, the initramfs mounts the actual root filesystem.
- After that, the temporary filesystem (initramfs) is discarded/unmounted.
- Kernel sets up the environment and transfers control to the first user-space process, typically init or systemd, which then continues to start all other user-space services.

# SystemD (The First Process) (ps -p 1)
- SystemD is the first user-space process, always started with PID 1 by the kernel to bring the system to a usable state.
- It initializes all required services and targets according to its configuration.
    The default target is usually a symlink:
    /etc/systemd/system/default.target
- Systemd uses targets.
    poweroff.target (runlevel 0)
    rescue.target (runlevel 1)
    multi-user.target (runlevel 3)
    graphical.target (runlevel 5)
    reboot.target (runlevel 6)
- Starts services in parallel
- Uses .service unit files to define services, dependencies, and startup order.
- Reads mount units (.mount files) and ensures filesystems like /home, /var, etc. are mounted & Handles swap activation.
- Brings the system to a specified target (like multi-user.target or graphical.target)
- And continues to manage services for the entire uptime of the system.       

# INIT
- In older systems, init was the first process with PID 1.
- The default init system was SysVinit
/sbin/init 
- SysVinit used /etc/inittab to decide which runlevel (0–6) to boot into.
- Runlevel determined system state:     * 
    3 -> multi-user, text mode
    5 -> multi-user, graphical mode
    0 -> shutdown
    6 -> reboot

# user-space
When the system is up and running, user space is where all normal processes, services, and applications run, while kernel space continues to handle low-level tasks like memory management, drivers, and process scheduling.