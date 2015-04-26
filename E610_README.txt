1. Android buid 
  - Download original android source code ( Jelly Bean 4.1 ) from http://source.android.com
  - Untar opensource packages of E610 android.tar.gz into downloaded android source directory 
    a)$tar xvzf android.tar.gz
  - And, merge the source into the android source code(Jelly Bean)
  - Run following scripts to build android
    a) source build/envsetup.sh
    b) choosecombo	
    c) make -j4                                                      
  - When you compile the android source code, you have to add google original prebuilt source(toolchain) 
    into the android folder 
    ( add prebuilt/linux-x86/toolchain/arm-eabi-4.4.3/bin to PATH )
  - After build, you can find output at out/target/product/generic  
  
2. Kernel Build
  - Untar opensource packages of E610 kernel.tar.gz using following command at the android folder
    a)$tar xvzf kernel.tar.gz
  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) 
    into the android folder.
  - cd kernel
  - export ARCH=arm
  - export TARGET_PRODUCT=m4_open_eu
  - export CROSS_COMPILE=~/android/android_prebuilt_toolchains/arm-eabi-4.7/bin/arm-eabi-
  - make m4-rev11_defconfig
  - make zImage

3. After Build, You Can find the build image at arch/arm/boot
