# linux

### filesystem hierarchy standard (fhs)

- fhs defines linux directory structure and what each folder is commonly used for
- common directories:
     - / (root directory)
     - /bin, /sbin
     - /etc
     - /home
     - /var
     - /usr
     - /opt
     - /dev
     - /tmp

**/** root directory
- top-level directory for the entire filesystem
- all of the other directories in fhs are in the root directory
- the root directory is owned by the root user, who has complete control over it
- structure and contents are crucial for system's stability and security
- many software packages install their files in specific directories under the root directory

**/bin** (binaries)
- contains essential binary executables that are needed during the boot process or in single-user mode
- generally accessible to all users

examples of binaries
- **ls** lists files and directories
- **cat** concatenates and displays files
- **cp** copies files and directories
- **mv** moves or renames files and directories
- **rm** removes files and directories

**/sbin** (system binaries)
- contains binary executables primarly used for system administration
- usually require root privileges to execute, since they involve system-level changes

examples of system binaries
- **fdisk** create partitions for hard drive
- **fsck** checks and repairs file system
- **init** initializes the system
- **reboot** reboots the system
- **shutdown** shuts down the system

**/etc** (configuration)
- stores configuration files for many system services and apps
- the contents of **/etc** can vary depending on the linux distro and installed software

content of **/etc**
- **/etc/passwd** user account information
- **/etc/shadow** user password hashes
- **/etc/group** group information
- **/etc/hosts** hostname and IP address mappings
- **etc/hostname** system hostname
- **etc/resolv.conf** dns resolver configuration
- **/etc/network/interfaces** network interface configuration (older systems)
- **/etc/sysctl.conf** system kernel parameters

**/etc** (service configuration)
- **/etc/apache2** apache web server configuration
- **/etc/nginx** nginx web server configuration
- **/etc/mysql/my.cnf** mysql database configuration
- **/etc/postgresql/postgresql.conf** PostgreSql database configuration
- **/etc/ssh/sshd_config** ssh server configuration

**/etc** (package managers)
- **/etc/apt/sources.list** apt package manager sources
- **/etc/yum.repos.d** yum package manager repositories
- why is it important?
    - **system behaviour** the configuration files in **/etc** directly influence how your system behave
	- **security** misconfigured files can pose security risks, so it's important to manage them with care
	- **customization** user can customize the system by editing these files
	- **troubleshooting** many system problems can be resolved by modifying configuration files
- caution
    - **backup** always back up any configuration files before making changes
	- **permissions** be careful of file permissions, as incorrect permissions can lead to system instability
	- **syntax** ensure the configuration files have correct syntax to avoid errors
	- **testing** test changes in a controlled environment before deploying time to a production system

**/home** (user personal space)
- primary location for user's files, documents and etc.

**/var** (variable data)
- stores variable data that changes frequently
- system logs, temporary files, mail spools, etc.
- common directories:
    - **/var/log** stores system and application logs. these logs can be used for troubleshooting or security analysis
	- **/var/mail** stores incoming mail for users
	- **/var/spool** contains spools for various services, including print jobs, mail, and news
	- **/var/lib** stores state information for various services and applications
	- **var/tmp** stores temporary files created by various applications
  - why is it important?
    - **system health monitoring** logs in **/var/log** provide insights into system performance and potential issues
	- **security analysis** logs can help identify security threats and unauthorized access attempts
	- **service operation** spool directories in **var/spool** are essential for services like printing and mail
	- **application state** **/var/lib** stores information needed for applications to maintain their state
  - important things to know
    - **regular cleanup** the **var/temp** directory should be cleaned regularly to prevent it from filling up
	- **log rotation** log files can grow large, so it's important to rotate them to save disk space
	- **permissions** ensure proper permissions on files and directories withing **/var** to protect system security
	- **backup** while not all contents of **/var** need to be backed up, it's important to back up critical logs and configuration files
	
**/usr** (user programs and libraries)
  - common directories
    - **/usr/bin** contains commonly used binaries accessible to all users
	- **/usr/sbin** contains system administration binaries, usually requiring root privileges
	- **/usr/lib** contains shared libraries used by programs
	- **/usr/local** used for locally installed software, often outside of the package manager
	- **usr/share** contains shared data files, such as documentation, icons, and configuration files
	- **usr/src** contains source code for various system utilities
  - why is it important?
    - **program execution** the binaries in **usr/bin** and **/usr/sbin** are essential for running programs
	- **library sharing** shared libraries in **/usr/lib** are used by multiple programs to reduce disk space and improve performance
	- **software installation** many software packages install their files in various subdirectories of **/usr**
	- **system documentation** the **/usr/share/doc** directory often contains documentation for system utilities and installed software
  - key points:
    - **read only** in many linux distros, **/usr** directory is mounted as read-only to prevent accidental modifications
	- **package management** package managers like apt and rpm manage the installation and removal of software packages, often modifying files within **/usr**
	- **user access** while some files in **/usr** are accessible to all users, others may require root privileges to modify

**opt** (optional software)
  - used to store additional software packages that are not part of the default system
  - designed for optional software installation, often from third-party sources
  - why use **/opt**?
    - **organization** it keeps optional software separate from the base system, making it easier to manage and remove
	- **isolation** it prevents conflicts between different software packages
	- **flexibility** it allows for easy installation and removal of optional software
  - typical structure of optional software in **/opt**
    - when software is installed in **/opt**, it typically creates a directory named after the software package. If user installed the mySql database server,
	it might be installed **/opt/mysql**. this directory will contain the software's binaries, libraries, configuration files and data
  - key points
    - **ownership and permissions** the ownership and permissions of files and directories within **/opt** can vary depending on the software
	- **package management** while some software packages can be installed using the system's package manager, others may require manual installation
	- **configuration** configuration files for software installed in **/opt** are often located within the software's directory
	- **cleanup** when removing software installed in **/opt**, it's important to remove all files and directories associated with the software

