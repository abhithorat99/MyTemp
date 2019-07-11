
# Appliance common code library
Copy all the Appliance common code directories from [https://github.com/geappliances/applcommon.applcommon](https://github.com/geappliances/applcommon.applcommon) in Appliance_common_code_library directory.  
 
Commit ID of Appliance common code used for library creation is **ea6c106692779edc28fb3e4c2b5c4aaa065510a2**  
Following directories are excluded from compilation:  
- Examples  
- Testing 
## Build Steps 
1. Download standalone tool chain for architecture 'arm' and api level '28' :   
	[https://developer.android.com/ndk/guides/standalone_toolchain](https://developer.android.com/ndk/guides/standalone_toolchain)  
	Android Tool chain version is **v4.9** 
2. Add the Android standalone tool chain path to the PATH variable  
   For e.g.  
	```bash
	export PATH=$PATH:/home/user/Project/android_toolchain/bin
	```

3. To configure what tools to use   
	```bash	
	source setcc
	```
4. To build code  
	```bash	
	make  
	```
	This will create Appliance common code static library **libappcommoncode.a** in directory **build**

