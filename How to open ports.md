# How to Open ports (a.k.a Firewall configuration)

## Google Cloud Platform

    <img src="https://app.dsrvlabs.com/images/git/img_google01.png">
    1. Click the Menu button in the top left corner
    2-1. Select "VPC network" menu
    2-2. Select "Firewall" sub menu   
    

    <img src="https://app.dsrvlabs.com/images/git/img_google02.png">
    3. Create a new firewall rule
    
    
    <img src="https://app.dsrvlabs.com/images/git/img_google03.png">
    4. Set your firewall rule name as "mina-dashboard". You can change the name of the firewall at your convenience, just make sure it is recognizable.
    5. Make sure your direction of traffic is set as "Ingress". You node needs to "Listen" to the requests from outside port.
    6. Set the targets as "All instances in the network". Alternatively you can choose a typical IP address option and add your public IP address of your node.
    7. Set the source of the IP range as "101.101.216.236". This is the IP address where we will request the information to your node.
    8. Check the TCP button and type "6060" for mina metrics and "9100" for node exporter.
    9. Click the create button and finish your firewall settings.
    

## 2. Amazon Cloud Services

    
    <img src="https://app.dsrvlabs.com/images/git/img_amazon01.png">
    1. Select "Security Groups" menu in the left menu section
    2. Click "Create security group" button in the top right corner
    
    <img src="https://app.dsrvlabs.com/images/git/img_amazon02.png">
    3. Type "mina-dashboard" as your security group name. You can change the name of the firewall at your convenience, just make sure it is recognizable.
    4. Type the description for the security group. This lets you recognize what the security group is for in the future.
    5. Add a new Inbound rule. Your type should be "Custom TCP", protocol as "TCP", port range as "6060", source as "Custom" and IP as "101.101.216.236/32"
    6. Add another Inbound rule. Your type should be "Custom TCP", protocol as "TCP", port range as "9100", source as "Custom" and IP as "101.101.216.236/32"
    
    <img src="https://app.dsrvlabs.com/images/git/img_amazon03.png">
    7. Go to the "Instances" menu on the left
    8. Click the "Actions" button in the top left corner
    9-1 Select "Security" menu
    9-2 Select "Change security groups" sub menu
    
    <img src="https://app.dsrvlabs.com/images/git/img_amazon04.png">
    10. Click the search button and select "mina-dashboard" security group you have previously created.
    11. Finish the firewall setting by clickcing the "Save" button.

## 3. Microsoft Azure

    3-1
    <img src="https://app.dsrvlabs.com/images/git/img_micro01.png">
    
    3-2
    <img src="https://app.dsrvlabs.com/images/git/img_micro02.png">
    
    3-3
    <img src="https://app.dsrvlabs.com/images/git/img_micro03.png">
    
    3-4
    <img src="https://app.dsrvlabs.com/images/git/img_micro04.png">
    
    3-5
    <img src="https://app.dsrvlabs.com/images/git/img_micro05.png">
    
    3-6
    <img src="https://app.dsrvlabs.com/images/git/img_micro06.png">
        

## 4. How to check whether your port is open
    <img src="https://app.dsrvlabs.com/images/git/img_signal01.png">