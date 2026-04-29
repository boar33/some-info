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
