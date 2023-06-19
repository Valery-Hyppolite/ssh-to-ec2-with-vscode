# ssh-to-ec2-with-vscode

**# HOW TO CONNECT TO YOUR EC2 INSTANCE USING VSCODE ON YOUR LOCAL MACHINE**
## Requirements:
* AWS EC2 instance running on AWS
* EC2 Key-Pair downloaded on the local machine
* PuTTyagen install

1. ## Set Up SSH Key with PuTTYagen
* open **PuTYYagent** locally, click **file**, then load the private key you want to convert.
* ![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/5d801b41-9ef8-4550-a31d-d5ef544e3134).
* After loading your private key pair, Select **Conversions > Export OpenSSH key** from the application menu.
* When the popup window appears asking if you want to save the key without a passphrase, select "**yes**".
* Navigate to **C:\Users\youruser\.ssh**, provide the key name, and click save.
![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/29479e55-a9e2-4b76-a62c-23df841c55ac)

## SET UP VSCODE TO CONNECT
Open VSCODE and click on the extension's icon to install remote ssh. 
In the search bar, search for "**Remote-SSH**" by Microsoft and install it

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/71b3829a-205e-4370-a726-4cf6667d2372)

On your Keyboard, press **Fn + F1** to bring up the command Palette, type in **remote-ssh**, and select **Connect to Host**

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/06a03c01-ed5d-4ff6-8418-dac84e2c3e6b)

Select **Add New SSH Host**

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/9ab63fce-a14a-4751-b7ce-27c3bea0fb66)

In the input bar, type **ec2-user@[ec2 public ipv4 dns]** then click enter.  **Get your ec2  Public IPV4 DNS on AWS**

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/97c78c96-aa37-4a09-9c29-f3e46c571f34)

select the **.ssh/config** file then click **Open Config** at the popup window in the bottom right. A config file should open.

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/4aa61ed6-0412-4f9a-8d3d-eab260ad6ca7)

In the config file, Change the **Host** to any name of your choice; Change **HostName** to your ec2 **Public IPV4 DNS**, leave **User** as it is, add **IdentityFile**, and provide the file path to your key-pair. 

In part one, we saved the keypair to this path **C:\Users\youruser\.ssh** . This current config file you have open automatically opened in the same path as the keypair, **C:\Users\youruser\.ssh,** therefore, just gives the name of the key pair. 

example

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/4dea421f-3a8f-4898-8664-fd5c9f4ad56f)

I named my key **project-web-app**, therefore I will just add that name to the end of the .ssh path and **SAVE** file.

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/db2188b6-6aea-44a7-9c00-72c8bd1ff16e)

**NOTE** For security reasons, HostName and keypair have changed. Make sure you add your ec2 hostname and your keypair name. 

# CONNECT TO EC2
Press **Fn + F1,** then select **Connect to Host**, then select the name of your **Host** (which you configured in the config file above) to connect your ec2 instance. 
I named my connection **aws-ec2-inventory**, so I selected this one.

If you have configured everything correctly, the connection should be established pretty quickly. if you get an error message, double-check your config file connection and make sure your HostName is correct and your key pair path.


![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/74d352b1-72e1-4aed-9d39-06ecb8ac6179)


Now, click** Open Folder**

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/650700ea-8c5a-45b1-82ac-c6dff6312389)

Then click **OKAY **to go to your home directory

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/972190cc-9744-46fb-bb15-d3d96add0d33)

**Now **you should see all files and folders on your ec2 instance and be able to edit them as you wish. 

![image](https://github.com/Valery-Hyppolite/My-Resume/assets/83102811/c2473705-f876-4420-b020-a9c7fb69eca3)
