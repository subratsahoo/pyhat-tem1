# pyhat-tem1
read temperture from hat 
import sys
import time
import select
import paramiko

host = '192.168.11.98'
username = 'pi'
password = ''
i = 1
ssh_client =paramiko.SSHClient()
ssh_client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
ssh_client.connect(host,username="pi",password="rourkela")

stdin,stdout,stderr=ssh_client.exec_command("sudo python ~/pycharm_project_844/pihat-test1.py")
[temp,pressure,humidity,date] = stdout.readlines()

print(temp)
print(pressure)
print(humidity)
print(date)
