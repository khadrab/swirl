<p align="center">
  <img src="assets/swirl-logo.png" width="100"/>
</p>

<h1 align="center">Swirl OS</h1>
<p align="center"><strong>A Lightweight Secure Operating System • Powered by Zenix Kernel</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/kernel-Zenix-blue" />
  <img src="https://img.shields.io/badge/status-early--development-orange" />
  <img src="https://img.shields.io/badge/architecture-x86--32-lightgrey" />
  <img src="https://img.shields.io/badge/license-MIT-green" />
</p>


---

## 🌀 Overview

**Swirl OS** is a lightweight, secure, and modular operating system built on top of the **Zenix Kernel**,  
a custom-built 32-bit kernel designed for speed, simplicity, and scalability.

Swirl OS focuses on:
- Fast boot and minimal overhead  
- Secure and predictable internals  
- Clean architecture and modular components  
- Running efficiently on low and mid-range hardware  

---

## ⚙️ Features (Current)

### 🔹 **Core System**
- Fully implemented GDT & IDT  
- ISR & IRQ handling  
- Physical Memory Manager (PMM)  
- Kernel heap (KHEAP)  
- Paging with identity mapping  
- Multiboot compliant  

### 🔹 **Drivers**
- PS/2 Keyboard driver  
- Serial port output  
- GOP framebuffer detection  
- Basic VESA detection  
- Intel HD 4600 GPU initialization (experimental)  

### 🔹 **Boot Process**
- GRUB Multiboot bootloader  
- Clean early-boot logs  
- Custom framebuffer console  

---

## ❓ Why Swirl OS?

Most existing OS kernels focus on either performance or flexibility — Swirl OS aims
to balance both, providing:

- A clean and modern kernel architecture
- Fast boot performance
- A predictable memory and interrupt model
- Easy extensibility for experiments or research
- A growing ecosystem targeting developers & creative tools

---

## 🚀 Build & Run

### **Requirements**
- GCC or Clang  
- NASM  


- GRUB tools (grub-mkrescue, etc.)  
- QEMU or any x86 emulator  

### **Build**
```bash
make clean
make
````

---

## 🔗 **Zenix Integration**

Swirl OS integrates with the **Zenix Runtime Layer**, a lightweight micro-subsystem designed to extend Swirl’s kernel capabilities.
Zenix is included as a linked repository and provides:

* Additional system services
* Experimental runtime features
* Low-level components used by the Swirl kernel

### 📁 Repository Link

**Zenix Repository:**
[Zenix Kernel](https://github.com/khadrab/zenix)

---

## 📁 Project Structure

```
/boot
  boot.asm
  bootloader.asm
  stage2.asm
  boot.h
  multiboot.h

/include
  stdint.h
  stdbool.h
  stddef.h
  types.h
  io.h
  /kernel
    config.h
    system.h
  multiboot.h

/kernel
  /core
    kernel.c
    init.c
    monitor.c
    panic.c
    main.h
    assert.h

  /hal
    cpu.c
    cpu.h
    gdt.c
    gdt.h
    idt.c
    idt.h
    interrupts.c
    io.c
    pic.c
    ports.c

  /mm
    pmm.c
    pmm.h
    vmm.c
    vmm.h
    paging.c
    heap.c
    heap.h

  /drivers
    /disk
      ata.c
      ahci.c
    /pci
      pci.c
    /keyboard
      keyboard.c
    /mouse
      mouse.c
    /serial
      serial.c
    /timer
      pit.c
      rtc.c
    /gpu
      gpu_detect.c
    /video
      framebuffer.c
      gop_fb.c
      vga_mode13.c

  /fs
    vfs.c
    file.c
    initrd.c
    /ext2
      ext2.c
    /fat
      fat.c

  /gui
    gui.c
    color.c
    antialiasing.c
    window_api.c

  /proc
    process.c
    scheduler.c
    thread.c
    switch.asm
    context.asm

  /ipc
    pipe.c
    message.c

  /syscall
    syscall.c
    handlers.c
    syscall_stub.asm

  /usermode
    usermode.c

  /apps
    app_manager.c
    /calculator
      calculator_app.c
    /text_editor
      text_editor.c

/lib
  /libc
    memory.c
    stdio.c
    stdlib.c
    string.c
  /libk
    bitmap.c
    hashtable.c
    list.c
    queue.c
  /math
    math.c

/tools
  mkinitrd.c
  mkfs.c

/docs
  architecture.md
  hal_guide.md
  memory_layout.md
  syscalls.md
```

---

## 🛠 Roadmap

### ✔️ Completed

* Kernel boot sequence
* Memory management (PMM, heap)
* Paging initialization
* Keyboard + serial drivers
* GOP framebuffer initialization
* Initrd loading

### 🔜 In Progress

* Virtual File System (VFS)
* ELF loader
* Usermode processes
* System call interface
* Window manager (future milestone)
* Package manager (beta phase)

---

## 🤝 Contributing

Contributions are welcome!
Since Swirl OS is still in its early development stage:

* Please open an Issue before submitting a Pull Request
* Follow the existing coding style: simple, modular, clean

---

## 📜 License

Swirl OS is released under the **MIT License**.

---

## 👤 Author

**Khadr Abdelrahman**
Creator of **Swirl OS**
Developer of the **Zenix Kernel**
