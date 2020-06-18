Code and files for **module 1**

## Organizing the C code
In order to be able to use the hardware based acceleration, we need to split the code between an host and a kernel.  The host runs on the server and uses APIs we'll discuss below to manage the data and command operations for the kernel.

Take now a look at the host code and notice the several APIs that are used.
Notice how the data is tranferred back and forth to the kernel an back.

Take a look at the kernel code.  This code will be compiled inside the Vitis tools and transformed into an hardware description that the Vivado tool can implement onto Xilinx devices. As we'll the goal on that code is to make it as efficient as possible in regards to the available hardware.

You could either import this design as a pre-setup project in the Vitis GUI or run make.
## Build and execute for Vitis
The Vitis GUI is based on Eclipse and allows you to customize the design.
<details>
  <summary>Click to expand! (instructions for GUI)</summary>
  
    ### Using Vitis via the **GUI**
    1. Open a terminal
    2. Setup and launch Vitis
    3, "File" menu -> "Import"...
    4. Accept the default of the Vitis project exported zip file and click "Next"
    5. Click "Browse" on the next window and navigate to the ./docs/module1_baseline/project directory
    6. Select the vitis_export_archive.ide.zip and click "Okay"
    7. Next window click "Finish"
 
</details>

<details>
  <summary>Click to expand! (instructions for make)</summary>
  
    ## Using **make**
    1. Open a terminal
    2. Setup Vitis
    3. Navigate to ./build
    4. Run make
       * make 
         * Without options, it will show the help
       * make build TARGET=sw_emu|hw_emu|hw
         * Builds for software or hardware emulation. The "hw" option runs the full compilation.
       * make run TARGET=sw_emu|hw_emu|hw
         * Executes for software or hardware emulation with "hw" running on the card after full compilation
	     * make clean
	       * delete files to start from a clean context
         
</details>