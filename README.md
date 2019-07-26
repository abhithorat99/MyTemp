
# GEA Application 
   This source code creates executable of GEA application  

## Build Steps 
1. Compile Appliance_common_code_library. This will create **libappcommoncode.a** in **build** directory.  

2. To build GEA application code  
	```bash	
	make  
	```
	This will create GEA application executable **gea3app** in directory.

3. To build Test application code goto directory **Test_app**  
	```bash	
	make  
	```
	This will create Test application executable **testApplication** in directory.  

## GEA Application Testing Steps
1. Run GEA application.  
	```bash	
	sudo ./gea3app  
	```

2. Run Test application.  
	```bash	
	sudo ./testApplication  
	```

3. Test Application is Menu driven. Menu will appear like :

	Enter command to send : 
	1. Read Status	2. Start Bake	3. Stop Bake

4. Select Action from Menu  	
