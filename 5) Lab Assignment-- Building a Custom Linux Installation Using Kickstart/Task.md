

You are given access to the Kickstart Web Generator shown in the screenshots above. Your task is to build a complete Kickstart automated installation file by configuring all required sections in the tool.

  

Follow the steps below carefully, and prepare a Kickstart file that meets all requirements:

1. Basic Configuration

Configure the following:

Set the default system language.

Choose the correct keyboard layout.

Select the correct time zone.

Enable or disable the UTC clock based on the installation environment.

Set and confirm a secure root password.

Decide whether the system should reboot automatically after installation.

Decide whether installation will be graphical or text mode.

1. Installation Source

Configure where the OS installer will load its packages from. Choose the correct installation source based on the environment you are using.

1. Disk Partitioning

Prepare the system disk as follows:

Clear the Master Boot Record.

Remove all existing partitions on the target disk.

Initialize the disk label.

Configure automatic or manual partitioning according to the installation needs.

Ensure that the partitioning scheme matches the system’s role.

1. Bootloader Configuration

Set up the system bootloader:

Decide whether to use a GRUB password.

Choose between BIOS (MBR) installation or UEFI.

Review the warning related to UEFI and automatic partitioning.

Add the required kernel boot parameters.

1. Package Architecture Selection

Choose the correct CPU architecture for the installation target from:

x86_64

aarch64

ppc64le

s390x

Ensure it matches the hardware or virtual machine you are installing on.

1. Networking Configuration

Configure whether the system will use DHCP or static networking.

Ensure the network interface will be active on first boot.

1. Security Settings

Configure system security policies:

Set SELinux mode (Active, Permissive, or Disabled).

Enable or disable the system firewall.

Choose which predefined services (HTTP, SSH, FTP, SMTP) should be allowed through the firewall.

Add the required custom ports that must be opened for the system's role.

1. Display Options

Decide whether the system will install a graphical interface or skip it.

Configure the First Boot Setup Agent (enabled or disabled).

1. Pre-Installation Script

Define a script that should run before installation begins. This script may perform tasks such as preparing disks or printing diagnostic information.

1. Post-Installation Script

Define a script that will run after the installation is completed. This script may be used to:

Install additional packages

Enable or start services

Modify configuration files

Prepare the system for operational use

1. Final Deliverable

Submit the following:

The generated full Kickstart file.

A screenshot of each configuration page you modified in the Kickstart generator.

A short explanation (1–2 sentences per section) describing why you chose each configuration.