# hypersing-cli-docker-engine-ubuntu

Pre-requisite  
  - Ubuntu System
  - Minimum 8GB RAM
  - Docker Engine for Ubuntu

# Docker Engine Installation 

To install the docker engine for Ubuntu follow the steps in the official documentation.

  https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

# Install Hypersign SSI CLI

> Remove the old hypersign-cli version, by typing below commands in your terminal
  ```
  sudo docker system prune -a
  rm -rf ~/.hypersign-ssi/
  ```

> To know latest version of ```hypersign-ssi cli``` please checkout realese here
  https://github.com/hypersign-protocol/hypersign-cli/releases

In this documentation, we will use ```v0.1.9``` hypersign-cli version

Install Hypersign SSI Cli by typing below command in your terminal.
```
wget -O hypersign-ssi.deb https://github.com/hypersign-protocol/hypersign-cli/releases/download/v0.1.9/hypersign-ssi_0.1.9.037a76a-1_amd64.deb && sudo dpkg -i hypersign-ssi.deb
```
![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/2b31fda0-8daa-40da-90a9-e4f8990fb14f)

Once you install it, check the version by typing 
```
hypersign-ssi
```
![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/91b00252-e2bf-4799-a9f8-317050b68df7)


Before you set up Hypersign SSI Cli make sure to Start your Docker Engine Deamon
> Note: If your system doesn't allow for a root user, you can use the sudo su command as shown below

```
sudo su
systemctl start docker
systemctl enable docker
systemctl restart docker
```
Below is the output of the above commands
![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/27cd90ff-931e-4d71-98a0-2a0433f53f10)

Now, you can start hypersign cli setup by following below commands

1. **hypersign-ssi setup**
   ```
   hypersign-ssi setup         
   ```
   
   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/0ef21df3-c854-4790-aec3-4abccc8b8289)

   Type Y and press the Enter key

   You will get the below services
   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/efccc0d8-7aed-4b18-93c8-d2e3c9d8194b)

   You can select any service, for now, we will select all services and press Enter Key

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/a1022124-76fa-4a84-abf4-5f2f93cb9cad)

   Proceed with the testnet for now, press the Enter key

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/07ff6edb-710c-465d-976b-9f9c16571f57)

   Now select the ```generate``` option from mnemonic setup

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/8ee8b574-fce6-4ba2-a5ad-b32c64d687e5)

   For setting up selected services, it takes time

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/d25b2fcd-6d01-4992-bbc3-5581c295a39b)

   Store the mnemonic in some secure place, so for next time you can enter the existing mneminic.
   Here is the mnemonic from above
   ```
   erase grocery wreck skirt depend curious electric envelope insane damage peanut december key marriage violin actor evidence fog remind key lady opera behind viable
   ```

   You will get below output once selected services setup successfull

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/3b11548c-f247-4dd6-bdd3-547b2c2ba479)

2. **hypersign-ssi start**
   
   Now, it's time to start the services

   Type
   ```
   hypersign-ssi start
   ```

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/5968efe8-ba2c-412b-905a-c3b266aae0a0)

   It will spin up the container and you will get the final output below

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/9431b665-2f12-40f9-ad2c-4fedf0eaa198)

   To check all containers are running type,
   ```
   docker ps
   ```

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/a9d8c0f9-6f69-499b-8bdb-07318397d691)

   You can navigate the service URL's to check it in browser

   📟 Entity Developer Dashboard : http://localhost:9001/

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/13bf0e4f-9083-47c7-841e-489c5a491b35)
   
   📟 Entity Developer Dashboard Service : http://localhost:3002/

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/a8b00644-24ff-47f1-9d50-9ee5379d1f16)

3. **hypersign-ssi stop**

   To Stop the currently running container, you can use the below command

   ```
   hypersign-ssi stop
   ```

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/07e49831-7938-4805-80b6-5a1d2567fcf2)

   You can check it by typing ```docker ps``` command

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/54fbb329-72a9-4a16-b369-2d80c15c8b14)

4. **hypersign-ssi clean**

   To Clean current containers, images, and data configuration use the below command and proceed with Yes.

   ```
   hypersign-ssi clean
   ```
   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/5754e2c2-5a76-486c-a84c-b606d1ed2edd) 

   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/ba86c889-4548-4215-8776-f805b064f77a)

   Once all services and data cleaned you will get below output
   
   ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/b7bbf222-9461-4e63-ac44-070182a2b488)

   Now we have installed the CLI and set up Hypersign Identity Infrastructure. Through this, We can use all the services in the local environment.
   
# What Next?

  Now to use Hypersign SSI infrastructure, Follow the below instructions:  

  1. Set up the Wallet and get the token balance in the Hypersign Wallet.

     1. Navigate to ```https://wallet-prajna.hypersign.id/```. Sign up with Google and you will get the below screen.

     ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/f9381ee4-015e-4c69-bd0a-443fae6ded56)

     2. Now Click on Transfer and you will see the transfer section. You can see the balance is 0. Copy your Wallet Address and get the balance for it by below (a) or (b) option

        ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/129fd6da-ec5d-40af-b8fe-dcbd16889ffb)

        
          1. Join our Discord server [prajna-faucet-1](https://discord.gg/S85P6crefd), you will directly enter into ```prajna-faucet-1``` channel. Now by typing this command ```$request <wallet-address>```               you will get a Token balance for your wallet address.
          2. Join our Telegram Channel  [here](https://t.me/hackdid) and send wallet address in chat

     Refresh your Transfer section in your wallet and you will receive a balance of 5 HID.

     ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/ce5da14c-08e3-4a83-b25f-8544909395d3)

     If you have any queries, feel free to ask in the Discord ```devs``` channel or in the Telegram group.

  2. To use SSI Playground in UI, navigate to ```http://localhost:9002/``` in your browser, and sign in with the Hypersign ID web wallet. 

     ![image](https://github.com/Raj6939/hypersing-cli-docker-engine-ubuntu/assets/67961128/6b84cbf0-86be-4f04-974c-43bde087de30)


  3. Once all things are ready, learn how to use SSI Playground through this SSI Workshop YouTube [Video](https://www.youtube.com/live/HCB5bObMlN4?si=3m1YputtXDNYQD3D)
    
     
     
     


     


     



     


     


     
     
  
  



  

   


   


    


   
   

  

   

   

   
   
   
   


   



   

   









   
