

# What is a shell and why should you learn to use it in Bioinformatics ?
A shell is a computer program that presents a command line interface which allows you to communicate with Unix and Linux operating systems. 
There are many reasons to learn about the shell:

**Essential for Bioinformatics** Many bioinformatics tools are accessible only through the command line. Others offer extended functionalities and configuration options that aren't available in their graphical interfaces. For example, advanced features in BLAST can only be accessed if you’re comfortable with the shell.

**Efficiency in Repetitive Tasks** Bioinformatics often involves working with large sets of data files, requiring repetitive actions. Using the shell, you can automate these tasks, saving time and enabling you to focus on more engaging parts of your work.

**Improved Accuracy** Repeating tasks manually, especially across many files, can lead to mistakes. However, a computer can execute the same operation hundreds or thousands of times without error, helping you avoid human mistakes. The shell makes your work more reproducible. When you carry out your work in the command-line (rather than a GUI), your computer keeps a record of every step that you've carried out, which you can use to re-do your work when you need to. It also gives you a way to communicate unambiguously what you've done, so that others can inspect or apply your process to new data.

**Access to Powerful Computing** Many bioinformatics analyses require significant computing resources, beyond the capabilities of a personal computer. These processes are often run on remote or cloud-based systems, which are accessed through the shell.

# How to access the shell locally
On a Mac or Linux machine, you can access a shell through a program called "Terminal", which is already available on your computer. The Terminal is a window into which we will type commands. If you're using Windows, you'll need to download a separate program to access the shell.

# How to access the shell on AWS
To save time, we are going to be working on a remote server where all the necessary data and software available. When we say a 'remote server', we are talking about a computer that is not the one you are working on right now. 

---

## 1. Create an AWS Account

1. Go to the [AWS website](https://aws.amazon.com/) and click on **"Create an AWS Account."**
2. Follow the instructions to sign up, providing your email address, credit card details, and identity verification.
3. After completing the setup, you’ll have access to the AWS Management Console.

---

## 2. Set Up an IAM User for Secure Access

AWS provides **IAM (Identity and Access Management)** to manage secure access. Instead of using the root account, create an IAM user with specific permissions.

1. In the AWS Management Console, go to the **IAM** service.
2. Select **Users** from the sidebar and click **"Add user."**
3. Name your user (e.g., `myadmin`) and enable **"Programmatic access"** to allow CLI access.
4. Click **"Next: Permissions,"** then choose **"Attach existing policies directly."**
5. Select a policy like **AdministratorAccess** or one with the needed permissions.
6. Continue through the steps, then download the **Access Key ID** and **Secret Access Key** for this user.

---

## 3. Set Up an SSH Key Pair (mandatory for EC2 Access)

To connect to EC2 instances, create an SSH key pair.

1. In the AWS Console, go to the **EC2** service, then select **Key Pairs** in the sidebar.
2. Create a new key pair, selecting **RSA** or **ED25519**.
3. AWS will prompt you to download the `.pem` file, which you’ll use to connect to instances securely.

---

## 4. Launch an EC2 Instance and Connect

1. In the **EC2 Dashboard**, click **Launch Instance**.
2. Follow the setup steps, selecting an Amazon Machine Image (AMI), instance type, and security settings.
3. Under **Key Pair**, select the key pair you created, then launch the instance.

**Connecting via SSH client on AWS**:
- Locate the instance's **Public IP address** or **DNS** in the EC2 dashboard.
- Use the following SSH command (assuming your `.pem` file is in the current directory):
  ```bash
  ssh -i "your-key-file.pem" ec2-user@your-instance-public-ip
  ```

---

## 7. Verify Your Access

Test access to AWS services by running a simple CLI command. For example, list your S3 buckets:
```bash
aws s3 ls
```
If the setup was successful, you’ll see a list of any existing S3 buckets, confirming your connection to AWS.

---



