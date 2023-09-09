# Linux Kernel Module Development 🛠️

## Setup & Directory Structure 📁
After downloading the git repository from the Udemy course on Netlink, you will discover specific folders:
- Navigate to the directory dedicated to the "Hello World" Linux kernel module.
- Inside, you'll find two primary files:
    - `Hello world `: The main module file. 📜
    - `makefile`: Used to compile the Linux kernel module. 🛠️
- Feel free to ignore other files for now.

## Anatomy of a Linux Kernel Module 🔍
Let's explore a typical Linux kernel module:
- Only **42 lines** of code for our "Hello World" demo! 🎉
- Key components:
    - **Header File**: Essential for writing any LKM. 📎
    - **Initialization Function**: Invoked when the module loads. Handles all initialization tasks. 🔌
    - **Cleanup Function**: Takes care of memory cleanup after module use. 🧹
    - **Registration**: Using `module init` and `module exit` functions, specify which functions act as initialization and cleanup. 🏷️
        - If omitted, the kernel defaults to `init module` and `cleanup module`.
    - **Metadata**: 
        - `module author`: Declares the module's creator. 👤
        - Description: Briefly describe the module's function. 📝
        - License: For instance, GPL for public license. 📜

## The Makefile 📄
Writing a `makefile` for a Linux kernel module is straightforward:
- Indicate the object file matching your source file.
- Specify the path to the Linux kernel headers during compilation.

## Loading, Running, & Unloading the Module 🔄
1. **Loading**: 
    - Use `lsmod` to check modules. Your module name should appear post-insertion.
    - `sudo insmod [module_name]` inserts the module.
    - `dmesg | tail` or `journalctl -k -f` to monitor real-time logs.
2. **Running**: Any print statements within the module go to journalctl. Use `journalctl -k -f` to view these logs live.
3. **Unloading**: 
    - Use `sudo rmmod [module_name]` to remove the module. 
    - The module should disappear from `lsmod` once unloaded.

---

### Interview Questions ❓

1. **What are the essential files when writing a basic "Hello World" Linux kernel module?**  
   Two main files are crucial: the main module file (in our case, `Hello world lcmc`) and the `makefile` used for compilation.

2. **Describe the two fundamental functions every Linux Kernel Module must have.**  
   Every LKM requires an initialization function (invoked when the module is loaded) and a cleanup function (handles memory cleanup post-usage).

3. **Why is the registration process vital in a Linux Kernel Module?**  
   The registration using `module init` and `module exit` informs the Linux kernel about the designated initialization and cleanup functions. If omitted, the kernel will default to `init module` and `cleanup module`.

4. **How do you load and unload a Linux Kernel Module?**  
   Use `sudo insmod [module_name]` to load and `sudo rmmod [module_name]` to unload.

5. **Where can you see the print statements from a Linux Kernel Module in action?**  
      Any print statements within the module go to `journalctl`. Use `journalctl -k -f` to view these logs live.

---

Wishing you success in your interviews! Remember, understanding the concepts and hands-on practice are key. Happy coding! 🚀📝🐧
