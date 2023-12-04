  # GRAFANA SETUP WITH INFLUXDB

## 1. Task Requirement:
- Garfana 
- InfluxDB


## 2. Environment Details:
- **OS:** Ubuntu 20.04

## 3. Tool and Technologies:

- Garfana 
- InfluxDB

## 4 . Definition of Tool:

  - **Garfana:** Grafana is an open-source, web-based platform used for monitoring, visualization, and observability of data from various sources.


-  **InfluxDB:** InfluxDB is an open-source, high-performance time-series database designed for efficiently storing, querying, and visualizing time-stamped data.

## Architecture Diagram
![Alt text](Screenshot%20from%202023-09-19%2014-01-02.png)





## 5 .  Command for the Setup or Configuration:

**Step 1  Update Your System**
<div style="page-break-after: always"></div>

```
 sudo apt update
 ```

![](SUDO%20UPDATE.png)
  
 
- **Sudo:** This command is used to superuser (root) privileges.

- **Apt:**  This is the package management command-line tool used on Debianbased distributions to handle packages.

- **Update:** The "Update" command is used to refresh or update information, such as software updates, to make sure it is current.

 ```
 sudo apt upgrade
 ```
 ![Alt text](upgrade.png) 

 -  **Upgrade**:The upgrade command is used to update or improve to a newer or better version.
   



**Step 2: Install InfluxDB**

 **Add the InfluxDB repository and GPG key:**

 ```python
  sudo curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
 ```

![](sudo%20apt-key%20add.png)


- -**s:**  stands for **"silent"** or **"quiet."** 

- **-L:**  stands for **"location."**

- **Curl:**  A command-line tool used to transfer data from or to a server.

- **https://repos.influxdata.com/influxdb.key:** This is the URL from which curl will download a file. It's fetching a file named influxdb.key from the repos.influxdata.com website over HTTPS.

- **|:**  This is a pipe . It takes the output from the command on the  (the curl command) and uses it as input for the command on the right.
  
- **sudo apt-key add:**  This command adds a new GPG key to the APT keyring. The key is taken from the input (in this case, the output of the curl command). The GPG key is used to verify the integrity and origin of packages from the repository



```python
echo "deb https://repos.influxdata.com/ubuntu focal stable" |sudo tee /etc/apt/sources.list.d/influxdb.list
```

![](stable.png)


- **echo:**  This command simply prints the string inside the quotes.

- **deb:** Indicates that it's a binary repository (for compiled software).

- https://repos.influxdata.com/ubuntu: Specifies the web address of the repository server.

- **tee:**  The tee command is used to write a standard input to standard output and a file.

- **focal:** Represents the version of Ubuntu for which the repository is intended (e.g., Ubuntu 20.04 is named "Focal Fossa").

- **stable:** Names the repository component, typically referring to stable releases of software.

<div style="page-break-after: always"></div>

```python
sudo apt update
```

![](up.png)

<div style="page-break-after: always"></div>

```python
sudo apt install influxdb
```


![](infulxdb.png)

- **install:** This tells the package manager to install the InfluxDB package.

- **influxdb:** This is the name of the InfluxDB package.
  

 **Step 3. Start and enable InfluxDB**

<div style="page-break-after: always"></div>

 ```python
 sudo systemctl start influxdb
 ```

- **systemctl:** This is the name of the systemd service manager.

- **start:** This tells the systemd service manager to start the InfluxDB service.

- **influxdb:** This is the name of the InfluxDB service.

<div style="page-break-after: always"></div>

```
 sudo systemctl enable influxdb
 ```
  
 ![](enable.png)

 - **enable:** This tells systemctl to enable the InfluxDB service.


```
sudo apt install influxdb-client
```
![Alt text](client_.png)


- **Influxdb-client:** This is the name of the influxdb client package.


![](client:.png)

**Step 4: Configure InfluxDB**

**Create a new InfluxDB user and database.**


```python
 influx
```

>**Inside the InfluxDB CLI, run the following commands to create a  database and user. Replace your username and yourpassword with your desired username and password:**



```python
CREATE DATABASE "mydb"
```
```python
USE mydb
```
```python
CREATE USER "maansi" WITH PASSWORD '1234' WITH ALL PRIVILEGES
Exit the InfluxDB CLI:
```


```python
exit
```

![](exit.png)



**Save and exit the configuration file, then restart InfluxDB**

```python
sudo systemctl restart influxdb
```

![](restart.png)

**Step 5: Access InfluxDB Web Interface**

**By default, InfluxDB runs on port 8086. Open your web browser and navigate to**

![Alt text](Screenshot%20from%202023-09-19%2017-23-18.png)


**Step 6: Install Grafana**


```python
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
```

![](Grafana.png)

```python
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 963FA27710458545
```

![](keyserver.png)


```python
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
```

![](wget%20.png)

```python
sudo apt update
```

![](apt.png)

```python
sudo apt install grafana
```
![](garfan.png)


**Step 6. Start and enable Grafana**
  
```python
sudo systemctl start grafana-server
```

```python
sudo systemctl enable grafana-server
```

![](server.png)

**Step 7: Access Grafana Web Interface**

**By default, Grafana runs on port 3000. Open your web browser and navigate to
http://localhost:3000**

![](login.png)

 **Step 8: Grafana Dashboard**

![Alt text](Screenshot%20from%202023-09-19%2017-39-22.png)


## 6. Reference Link

- https://www.youtube.com/watch?v=siyIExDV0fw&ab_channel=VamsiA


