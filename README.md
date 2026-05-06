# **Project Introduction** #
**Static Website Hosting**is a simple web hosting method used to deliver static web pages containing HTML, CSS, and JavaScript files directly to users through a web server.

In this project, **a monolithic architecture** is implemented where both the website files and the **Nginx web server** are deployed on a single Amazon Web Services EC2 instance. The static website files are placed in **the Nginx root directory (/usr/share/nginx/html)**, enabling the server to efficiently serve web pages to users through the EC2 instance’s public IP address.

# **1.Architecture Overview**
![Architecture Digram](/Architecture.png)

# **2.Instance Setup**

## 2.1 Launch Instance
![Launch Instance](/s1.png)

## 2.2 Name and OS
### Name: `static-website` 
### OS : `Amazon Linux`

![Name](/s2.png)

## 2.3 AMI and Instance Type
### AMI :`Default`
### Architecture :`Default`
### Instance Type : `t3.micro`(2CPU 1GB Memory)

![AMI](/s3.png)

## 2.4 Key and Network And Launch Instance
Key : `north-v-key.pem` (Exiting One)

Security Group : `Launch-Wizard-3` (Exiting One)
![network](/s4.png)

## 2.5 Connect Instance
![instance](/s5.png)

## 2.6 Copy SSH Client Link 
![ssh](/s6.png)

# 3.Installing Packages
## 3.1 Open GitBash Where Your Private Is Stored(.pem) and Connect Instance With SSH Key

![gitbash](/s7.png)

## 3.2 Update Packages

```jsx
sudo yum update
```
## 3.3 Install Nginx

```jsx
sudo yum install nginx -y 
``` 
## 3.4 Start Nginx

```jsx
sudo systemctl start nginx
```

## 3.5 Enable Nginx

```jsx
sudo systemctl enable nginx
```

## 3.6 Check Status Nginx

```jsx
sudo systemctl status nginx
```

# 4. Running Static App

## 4.1 Go To Nginx Default Directory

```jsx
cd / usr / share / nginx / html;
```

## 4.2 Remove Existing Files

```jsx
 sudo rm -rf *.html *.png icons
```

## 4.3 Create Index, Style & Script FIles

```jsx
sudo vim index.html
sudo vim style.css
sudo vim script.js
```
![index](/s8.png)

![style](/s9.png)

![script](/s10.png)

## Restart Nginx
```jsx
sudo systemctl restart nginx
```
# 5. Access on Browser
## 5.1 Hit Public Ip on Browser
```jsx
107.20.109.139
```
![Bloom](/s11.png)

![products](/s12.png)

![About](/s13.png)

# 6.Summary 
Static website deployment refers to the method of publishing web pages containing only frontend technologies such as HTML, CSS, and JavaScript on a web server. In this setup, an Amazon Web Services EC2 instance is used to host the website with Nginx acting as the web server. The website files are placed inside the Nginx root directory, enabling users to access the website through the instance’s public IP address. This deployment model is efficient, easy to maintain, and suitable for lightweight web applications without server-side functionality.
