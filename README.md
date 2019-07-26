
# GEA Application 
   This source code creates executable of GEA application  

## Build Steps 
1. To build Appliance common code library, GEA application and Test application execute following command   
	```bash	
	make all  
	```
	This will create GEA application executable at path **gea_application/gea3app** ,  Appliance common code library at path **Appliance_common_code_library/build/libappcommoncode.a** and Test application executable at path **Test_app/testApplication**.

2. To build only GEA application execute following command  
	```bash	
	make app  
	```
	This will create GEA application executable at path **gea_application/gea3app**  

## GEA Application Testing Steps
1. To install the ADB execute the following command from the terminal  
	```bash	
	sudo apt-get install android-tools-adb android-tools-fastboot  
	```

2. To push GEA Application, Test application and run script on android platform execute following command  
	```bash	
	make install  
	```
	This will push GEA Application, Test application and run script in **data/local/tmp** directory  

3. Got **data/local/tmp** directory and run **run.sh** script  
	```bash	
	./run.sh  
	```
	This will run GEA application in background and Test application in foreground.

4. Test Application is Menu driven. Menu will appear like :

	Enter command to send : 
	1. Read Status	2. Start Bake	3. Stop Bake

5. Select Action to be performed from Menu  	
