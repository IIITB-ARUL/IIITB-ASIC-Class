<details> <summary>Day0
</summary> 
<details> <summary>Steps to install iverilog
</summary> 
  Update Package List:
Open a terminal and run:

```
sudo apt update
sudo apt install iverilog

```

I have installed iverilog

![Screenshot from 2023-07-31 10-00-34](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/cc5c5cc1-34f4-4a34-b7c5-d6e083917f14)


</details>

<details> <summary>Steps to install gtkwave</summary>

Update Package List
Open a terminal and run:
```
sudo apt update
```
Install GTKWave:
```
sudo apt install gtkwave
```
![Screenshot from 2023-07-31 10-01-15](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/fe9ee1da-ece4-4e21-aca2-e2fa6001356b)
</details>

 <details> <summary>Steps to install Yosys</summary>

Update Package List
Open a terminal and run:
```
sudo apt update
```
Install Yosys:
```
sudo apt install yosys
```
![Screenshot from 2023-07-31 10-01-35](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/9d294e21-a6ac-4a47-aeff-8e5f020c7585)

</details>

<details><summary>Steps to install ngspice</summary>


Dependencies Installation:

```
sudo apt-get install build-essential
sudo apt-get install libxaw7-dev
```


Download the tarball file from link:
 
  https://github.com/The-OpenROAD-Project/OpenSTA


Unpack the file by using the following commands:

```
tar -zxvf ngspice-37.tar.gz
cd ngspice-37
mkdir release
cd release
../configure  --with-x --with-readline=yes --disable-debug
make
sudo make install
```


![Screenshot from 2023-08-05 21-44-33](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/7e4a2030-6cb4-4f71-a7ae-e149cb20e916)

</details>

<details><summary>Steps to install Magic</summary>
Install Magic:

```
sudo apt-get install m4
sudo apt-get install tcsh
sudo apt-get install csh
sudo apt-get install libx11-dev
sudo apt-get install tcl-dev tk-dev
sudo apt-get install libcairo2-dev
sudo apt-get install mesa-common-dev libglu1-mesa-dev
sudo apt-get install libncurses-dev
git clone https://github.com/RTimothyEdwards/magic
cd magic
./configure
make
make install
```

  ![Screenshot from 2023-08-05 21-35-52](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/c37effb6-a016-4dc9-914a-fa8bd6e72f38)

</details>
<details><summary>Steps to install OpenLane</summary>
Install Dependencies:

```
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip make git
```
Docker Installation:
```

sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io

sudo docker run hello-world

sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot 
```

![Screenshot from 2023-08-05 21-32-09](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/51278a13-82f2-4a94-9180-2815d9c7498c)


</details>
<details><summary>Steps to install PDKS and tools</summary>
Proceed with the following commands:
  
```
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```

</details>

</details>
