
# GEA Application 
   This source code creates executable of GEA application  

## Build Steps
1. Add the Android standalone tool chain path to the PATH variable  
   For e.g.  
	```bash
	export PATH=$PATH:/home/user/Project/android_toolchain/bin  
	```
2. To configure what tools to use   
	```bash	
	source setcc
 	``` 
3. To build Appliance common code library, GEA application and Test application execute following command   
	```bash	
	make all  
	```
	This will create GEA application executable at path **gea_application/gea3app** ,  Appliance common code library at path **Appliance_common_code_library/build/libappcommoncode.a** and Test application executable at path **Test_app/testApplication**.

4. To build only GEA application execute following command  
	```bash	
	make app  
	```
	This will create GEA application executable at path **gea_application/gea3app**  

## GEA Application Testing Steps
1. To install the ADB execute the following command from the terminal  
	```bash	
	sudo apt-get install android-tools-adb android-tools-fastboot  
	```
2. Connect Type C cable to **Type C Port1** of th board and PC   

3. On Android Platform, to get super user access execute following command  
	```bash	
	su  
	```
2. To push GEA Application, Test application and run script on android platform execute following command  
	```bash	
	make install  
	```
	This will push GEA Application, Test application and run script in **data/local/tmp** directory  

3. Go to **data/local/tmp** directory and run **run.sh** script  
	```bash	
	./run.sh  
	```
3. Go to **data/local/tmp** directory and run **run.sh** script  
	```bash	
	./run.sh  
	```
	This will run GEA application in background and Test application in foreground.  

4. Test Application is Menu driven. Menu will appear like :  

	Enter command to send :   
	1. Read Status	2. Start Bake	3. Stop Bake  

5. Select Action to be performed from Menu  	
