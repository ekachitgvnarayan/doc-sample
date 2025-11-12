# How to Install SQL Database with Podman

## Step 01

Create an Oracle account and Sign-in to the account from [Here](https://container-registry.oracle.com/)

---

## Step 02

1. podman machine init
2. podman machine start

---

## Step 03

Run this command
`podman login container-registry.oracle.com`
> Make sure to generate Auth Token from Oracle link and paste it as password

---

## Step 04

run this in the terminal to pull the oracle db image
`podman pull --tls-verify=false container-registry.oracle.com/database/free:latest`

---

## Step 05

```
  podman run -d \
  --name oracle-db \
  -p 1521:1521 -p 5500:5500 \
  -e ORACLE_PWD=[YourDesiredPasswordHere…] \
  container-registry.oracle.com/database/free:latest
```
> Put the Password to your desired password

---

## Step 06

### If you are in Podman Terminal
`podman logs -f oracle-db`

### If you use Podman Desktop

Open the Podman desktop and open oracle container in Containers section on the left. 
Check the logs and see if you can see **DATABASE IS READY TO USE!**

---
