
# set their passwords to expire after 60 days
  You will first start off by using the linux command "sudo /etc/login.defs" and chaange the expire date to 60 days.

![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/5ad831715e6f16b50ec306cf84185a0a1fcfe634/Creating%20new%20user/60%20days%20password%20expire.png)
  
# ensure all these users get a home directory in /home
  In linux RHEL 9 it should already be set to create a home directory you can verify by checking in the following .txt file "sudo /etc.login.defs"

![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/5ad831715e6f16b50ec306cf84185a0a1fcfe634/Creating%20new%20user/create%20home%20.png)
# create a group sales and make linda and laura members of that group
  To create linda and laura and add them to the sales group:
  
  "sudo adduser linda -G user,sales"
 
  ![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/e5201272f55b974560c70359233371446ff6b3db/Creating%20new%20user/linda%20added%20to%20group.png)
  
 
  "sudo adduser laura -G user,sales"
  
  ![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/e5201272f55b974560c70359233371446ff6b3db/Creating%20new%20user/Laura%20added%20to%20group.png)
# create a group account and make anna and anouk members of that group
  To create anna and anouk and add them to the account group:

  
  "sudo adduser anna -G user,account"
  
  ![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/e5201272f55b974560c70359233371446ff6b3db/Creating%20new%20user/anna%20added%20to%20group.png)

  "sudo adduser anouk -G user,account"
  
  ![Alt Text](https://github.com/JamahdPerry99/Linux-study/blob/e5201272f55b974560c70359233371446ff6b3db/Creating%20new%20user/anouk%20added%20to%20group.png)
# Also create a group users, and make all four users memebrs of that group as a secondary group

This was done in the following steps above(with screenshots) but to verify the users have been added you can do the following command:

"grep anouk /etc/group"

"grep anna /etc/group"

"grep laura /etc/group"

"grep linda /etc/group"



# Use input redirection to set the passwords for these users to "password"
You will use the following command to change the passwords of everyone:

for i in linda laura anna anouk; do echo password | sudo passwd --stdin $i; done
