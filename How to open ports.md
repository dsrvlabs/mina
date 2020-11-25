# How to Open ports (a.k.a Firewall configuration)

### 1. Google Cloud Platform

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_google01.png"></img>

1. Click the Menu button in the top left corner      
2. Select "VPC network" menu, Select "Firewall" sub menu  

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_google02.png">
     
3. Create a new firewall rule

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_google03_1.png">
       
4. Set your firewall rule name as "mina-dashboard". You can change the name of the firewall at your convenience, just make sure it is recognizable.
5. Make sure your direction of traffic is set as "Ingress". You node needs to "Listen" to the requests from outside port.   

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_google03_2.png">

6. Set the targets as "All instances in the network". Alternatively you can choose a typical IP address option and add your public IP address of your node.  
7. Set the source of the IP range as "101.101.216.236". This is the IP address where we will request the information to your node.  
8. Check the TCP button and type "6060" for mina metrics and "9100" for node exporter. 
9. Click the create button and finish your firewall settings.


##



### 2. Amazon Cloud Services

    
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_amazon01.png">
 
1. Select "Security Groups" menu in the left menu section
2. Click "Create security group" button in the top right corner
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_amazon02.png">
 
3. Type "mina-dashboard" as your security group name. You can change the name of the firewall at your convenience, just make sure it is recognizable.
4. Type the description for the security group. This lets you recognize what the security group is for in the future. 
5. Add a new Inbound rule. Your type should be "Custom TCP", protocol as "TCP", port range as "6060", source as "Custom" and IP as "101.101.216.236/32"
6. Add another Inbound rule. Your type should be "Custom TCP", protocol as "TCP", port range as "9100", source as "Custom" and IP as "101.101.216.236/32"<br/>
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_amazon03.png">

7. Go to the "Instances" menu on the left
8. Click the "Actions" button in the top left corner
9. Select "Security" menu, Select "Change security groups" sub menu
  
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_amazon04.png">
 
10. Click the search button and select "mina-dashboard" security group you have previously created. 
11. Finish the firewall setting by clickcing the "Save" button.



##




### 3. Microsoft Azure

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro01.png">

1. Type "Firewall" in the search bar
2. Click "Firewall Policies" in the Services Menu
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro02.png">
 
3. Click "Create Azure Firewall Policy" button
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro03.png">

4. Select the resource group of your node
5. Type the name of the firewall policy as "mina_dashboard" and select the region same as your node
6. Click the "Next" button to proceed to DNS Settings
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro04.png">
 
7. Enable DNS settings
8. Click the "Next" button to proceed to Rules
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro05.png">

9. Add a rule collection at the "Parent policy" section
10. Type "mina_dashboard" for the name of the rule
11. Set the priority of the rule as "1000"
12. For the first rule, use "mina_dashboard" as the name, "IP Address" as the Source type, "Your node IP address" as Source, "TCP" as Protocol, "6060" as Destination Ports, "IP Address" as Destination Type and "101.101.216.236" as Destination.
For the second rule, use "node_exporter" as the name, "IP Address" as the Source type, "Your node IP address" as Source, "TCP" as Protocol, "9100" as Destination Ports, "IP Address" as Destination Type and "101.101.216.236" as Destination.
13. Click "Add" to add the rule to the firewall policy
14. Click "Review + create" to take a review of the firewall policy
 
&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_micro06.png">

15. Click "Create" to finish setting your firewall policy



##




### 4. How to check whether your port is open

&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://app.dsrvlabs.com/images/git/img_signal01.png">

Access to the page "https://www.yougetsignal.com/tools/open-ports/" and type your IP Address in the Remote Address box and type port 6060 and 9100 each to confirm that the port is open.
