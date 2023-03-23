How to create a GCP VM and use SSH keys to access it!
In very simple terms cloud computing is the delivery of computing services over the internet, such as servers, storage, databases, networking, software, and analytics. When you’re using this services without the requirement to pay and manage this infrastructure, you’re probably availing cloud computing services.
There are three main types of cloud computing:
Infrastructure as a Service (IaaS): when you’re renting infrastructure such as servers, data storages. Users have full control over the operating system and applications, while the cloud provider is responsible for the underlying infrastructure.
Platform as a Service (PaaS): when you’re providing the code and the cloud provider is handling the infrastructure.
Software as a Service (SaaS): when you’re using a software hosted by a cloud provider.
Using cloud computing is great because it provides benefits such as scalability, cost savings, availability and security services.
Nowadays, there are a lot of cloud service providers. This article will be primarily focused on Google’s cloud servicing providers.
Create a VM instance using Google Cloud
By following this steps you can create a VM instance with your desired operating system of choice.
Go to the Google Cloud Console at https://console.cloud.google.com/ and log in using your Google account credentials. If you don’t have
Once you’re logged in, you will be taken to the Cloud Console dashboard. From there, click the “Create Project” button in the top navigation bar.
In the “Create a project” text box, enter a name for your project and click “Create”.
Once your project is created, you will be taken to the project dashboard. From there, click the navigation menu (the three horizontal lines in the top left corner) and select “Compute Engine” from the list of services.
In the Compute Engine dashboard, click the “Create Instance” button to create a new virtual machine.
In the “Create a new instance” dialog box, enter a name for your instance and select a region and zone for your instance. You can also choose the machine type and select any additional settings you want to configure.
Once you have selected all you want, click the “Create” button to create your VM instance.
By following all the steps you will have successfully created your VM instance!
Using SSH keys
Here are the steps to use SSH to access a VM in Google Cloud Platform (GCP):
Open the Google Cloud Console at https://console.cloud.google.com/.
Once you’re logged in, navigate to the VM instance that you have already created.
You can use your local terminal on your PC to generate SSH keys by using this command: ssh-keygen -t rsa -f ~/Desktop/key -C USERNAME
This will create an SSH key pair on your desktop with the names ‘key’ and ‘key.pub’
Click the “Edit” button on top.
In the “Edit instance” dialog box, scroll down to the “SSH Keys” section and click “Add Item”.
Copy the contents of the “key.pub” file on your Desktop and paste them into the textbox.
Open your SSH client and create a new connection to your VM instance. Use the VM instance’s external IP address or hostname as the connection address.
Open your local terminal and enter this command: 
ssh -i ~/Desktop/key user@EXTERNALIP_VM
user@EXTERNALIP_VM where user is the user you specified when creating your keys and EXTERNALIP_VM is the IP address you are provided in the console.
Once you have connected to the VM instance, you can execute commands and manage the instance as if you were using a local command line interface.
If you’ve followed the instructions, congratulations you’ve connected into your VM through SSH which has helped you achieved security.
Conclusion
The purpose of this blogpost was to make you more aware of Cloud Computing and its benefits as well as provide you with a small exercise that is conducive to learning.
Cloud computing is an emerging field and the possibilities with cloud are endless and as aspiring technicians we must stay in the loop.
