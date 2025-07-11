# Mini-project-Advanced-Linux-Commands

# Advanced Linux Commands
### File Permissions and Access Rights

##  Project Objective
### To establish a well practical understanding of Linux file permissions and user access control through the application of essential commands such as ls, chmod, chown, adduser, and usermod. This knowledge is vital for system administrators and DevOps engineers to secure file access on Linux systems.

 # Stages are
 
 ## 1. Understanding File Permissions in Linux
#### Linux uses symbolic and numeric methods to represent file permissions.

<img width="840" height="480" alt="1 Rwx" src="https://github.com/user-attachments/assets/30846ce1-9804-4941-bf31-393ac4853fa0" />

## Focus on Key Concepts
#### User Classes:

- User (u) – The file owner
- Group (g) – Users who share group ownership
- Others (o) – Everyone else

#### Permission Types:

- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1

#### Examples:

- rwx = 7
- rw- = 6
- r-- = 4

## 2. Practical Demonstration of Permission Types

### Step 1: Start a New File

##### touch script.sh
##### ls -latr script.sh

<img width="840" height="480" alt="2 touchscript-sh" src="https://github.com/user-attachments/assets/d5eda909-4b41-4c81-b5d4-de96e90c31b0" />

 ### Step 2: Add all Execute Permission to All Users

##### chmod +x script.sh
##### ls -latr script.sh

<img width="840" height="480" alt="3 chmod+x" src="https://github.com/user-attachments/assets/87744a0f-5ee3-4ca4-9bdf-293a46e7146a" />

### Step 3: Setting Permissions Using Numeric Notation

##### chmod 755 script.sh
##### ls -latr script.sh

<img width="840" height="480" alt="4 chmod755" src="https://github.com/user-attachments/assets/f4afac62-43d2-4952-9429-436ce5ff2eab" />

### Step 4: Give Full Permissions to All Users (777)

##### chmod 777 note.txt
##### ls -latr note.txt

<img width="840" height="480" alt="5 Chmod777notetxt" src="https://github.com/user-attachments/assets/9af2f518-b484-4cd9-9edc-49b976bc1c1e" />

##  3. Changing File Ownership
### Step 5: Create a File and Change Ownership
#### Let's create group developer to use :

####### sudo groupadd developer
####### cat /etc/group

<img width="840" height="480" alt="6 Adddevelopergroup" src="https://github.com/user-attachments/assets/e1cd7071-e484-4eed-839a-15ec34e5e1b3" />

<img width="840" height="480" alt="7 Developergroup" src="https://github.com/user-attachments/assets/9f4e70b6-8bbf-447d-962d-0a4c24da20f7" />

### We would now create user John with useradd and assign him to developer group:

###### sudo useradd -c John -g developer john
###### cat /etc/passwd

<img width="840" height="480" alt="8 Adduserjohn" src="https://github.com/user-attachments/assets/fe72afb4-cb7c-4099-be96-ba5dfbc1df5c" />

<img width="840" height="480" alt="9 etc-passwduser" src="https://github.com/user-attachments/assets/631029a4-f07c-451d-bc2c-89a7caa989b3" />

### Create a test file:

###### touch filename.txt

<img width="840" height="480" alt="10 touchfilename-txt" src="https://github.com/user-attachments/assets/2752281f-7c2a-4b9c-ad03-b38b02b817d3" />

### We would assign the file to John

##### sudo chown john:developer filename.txt
###### ls -latr filename.txt

<img width="840" height="480" alt="11 Addchownfilename-txt" src="https://github.com/user-attachments/assets/db507ef8-7d8b-4670-bb5e-3945e4b780d9" />

## 4. Using sudo and Switching to Root
#### Step 6: Become Superuser Temporarily
###### sudo -i

<img width="840" height="480" alt="12 switchtosuperuser" src="https://github.com/user-attachments/assets/3f0ac7f5-de10-4bdd-bdc9-fba55d5302ff" />

#### Exit root shell:

###### exit

<img width="840" height="480" alt="13 ExitSuperUser" src="https://github.com/user-attachments/assets/7140e6fa-5307-46db-84f7-8f67d4fc624d" />

## 5. User and Group Management in Linux
#### Step 7: Create a New User
###### sudo adduser testuser1
###### Follow the prompts to enter:

- ###### Password
- ###### Full name
- ###### Room number
- ###### Phone numbers

<img width="840" height="480" alt="14 addtestuser1" src="https://github.com/user-attachments/assets/02e58434-7a8d-42bb-b8d9-9c7eb74d181c" />

### Step 8: Verify the Home Directory Creation
##### ls -ld /home/testuser1

<img width="840" height="480" alt="15 viewtestuser1director" src="https://github.com/user-attachments/assets/0a170284-a6d7-41e0-9f45-559456ea7671" />

### Step 9: Grant Sudo Privileges
##### sudo usermod -aG sudo testuser1

<img width="840" height="480" alt="16 MakeTestUserAdmin" src="https://github.com/user-attachments/assets/b31cf543-9b16-4754-ae73-3a48947dd9e5" />

##### groups testuser1

<img width="840" height="480" alt="17 Verifytestuser1privilege" src="https://github.com/user-attachments/assets/6ff0b600-33fa-4bbe-9e7e-fdfc363f3c9b" />

## 6. Bonus: File Type Recognition
###### When listing files with ls -latr, note the first character in the output:

- #### for regular file
- #### d for directory
- #### l for symbolic link

- ###### ls -latr

- <img width="840" height="480" alt="18 lslatrexplained" src="https://github.com/user-attachments/assets/fb62bdeb-c566-470f-be13-1832fa601059" />


#### Summary Checklist

|Table Name| Description|
|-----|-----|
|Step| Task| Screenshot?|
|1	|Create file and check default permissions	✅ |
|2	|Grant execute permission with chmod +x	✅|
|3	|Use numeric chmod 755	
|4	|Apply full permissions chmod 777	✅|
|5	|Change ownership with chown	✅|
|6	|Become superuser with sudo -i	✅|
|7	|Add a new user with adduser	 ✅|
|8	|Confirm home directory creation	 ✅|
|9	|Grant sudo privileges	✅|
|10	|ls -latr explanation	 ✅|





















   
 

 
