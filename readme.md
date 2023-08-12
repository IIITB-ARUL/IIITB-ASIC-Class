## ASIC




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
<details>
<summary> Day1 </summary>

  **Introduction to verilog RTL Design and Synthesis:**

Register Transfer Logic is a representation of the digital circuit at an abstract level.At the RTL level, designers describe the behavior and functionality of a digital system using a hardware description language (HDL) such as Verilog.

**Simulator:**


**Testbench:**

The functionality of the design block can be tested by applying **stimulus** and checking results.The stimulus block is called as testbench.


![Testbench](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/ddc87d0b-32cc-405d-938b-0b17be79d182)


**Working of Simulator:**


**Introduction to opensource simulator iverilog:**


**Environment Setup:**

Here  we will look into toolflow setup and files setup which are needed to run the lab.
Create a directory named VLSI and git clone(make a clone or copy of files repo at in a new directory to a local machine) the necessary files:

```
mkdir VLSI
git clone https://github.com/kunalg123/vsdflow.git
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```

Once you run the commands the corresponding directories will be created.To navigate through the directories and view the  cloned files use the commands shown in the following image.


![Navigate](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/f4175d80-dab8-4911-9975-0db0b1870d5b)


In this section we will first focus on the simulation of the design using **iverilog**.You can see the design files or source files and testbench files in the above image which we are going to use in this lab.


**Working with iverilog and gtkwave:**

Now we are going to load the design file and testbench file in iverilog.To access the file and to simulate it you should move to the **verilog_files** directories as showed in the previous image.

**Simulation:**

We shall compile a 2:1 mux by loading a design file named good_mux.v and its associated testbench file tb_good_mux.v by using the following command:

```
iverilog good_mux.v tb_good_mux.v
```
Now an executable file is created.By executing it(using below command),It will dump a vcd file as you can clearly see in the below image:

```
./aout
```

![Screenshot from 2023-08-09 01-51-42](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/dae54b81-6e1d-4cfc-89da-a44403cf90c2)


Now to view the waveform use the following command:

```
gtkwave tb_good_mux.vcd
```

![Screenshot from 2023-08-09 01-59-36](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/77c9550e-071a-45f5-ab1c-dee7b7ba2088)

To access and edit the module file,use the following command:

```
gvim tb_good_mux.v -o good_mux.v
```

![Screenshot from 2023-08-09 02-19-27](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/545294b9-af11-4d8d-883f-c960a4e1afa7)


**Introduction to  Yosys and logic synthesis:**

Yosys is an open-source software framework for RTL synthesis and formal verification of digital designs.

**Synthesis:**

 It is the process of converting the high-level description into an RTL representation that defines the functional blocks, interconnections, and register transfers within the design. This representation is often in the form of a hardware netlist, which is a list of interconnected logic elements.
 During synthesis, various optimization techniques are applied to improve the design's performance, power efficiency, and area utilization.
 
 The first step synthesizer is going to do is a syntactical check then it will start mapping the design.
 **Example:**

![Synthesis example](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/28825050-136b-4778-975e-f23e4b550558)


The conversion of RTL in terms of the standard cells  gates available in the **.lib**.

1.Module maps to the top level ports of the design.

2.The assign statement becomes the mux.

3.The always block  becomes the flipflop.


    
**What is .lib?**

.lib file is a collection of logical modules which includes all basic logic gates. It also contains different flavors of the same gate (2 input AND, 3 input AND – slow, medium and fast version).
This gates will be more than sufficient to form any logical function.

**Purpose of slower cells and faster cells:**



**Introduction to Yosys lab:**

**Steps for Synthesis:**
Move to the directory verilog_files and invoke yosys:

```
cd VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files/
yosys
```


![invoke](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/30eeeaaf-14d5-44f0-95f1-be26863eff23)


Now to read the library and design files,give the following cmmand in the yosys prompt:

```
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog good_mux.v
```


![readlib](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/2f487b4b-551d-408a-9216-adb8706d33f5)


Synthesize the module using command:

*synt -top <name.v>*

Here we will synthesize a mux,

```
synth -top good_mux.v
```

**Note:** If the design is spanning more than one  file append remaining file names to the above command.

![Synth](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/afe0511e-123f-4696-8832-486a97745218)

**abc command:** 

This command converts our RTL file into set of gates,i.e., the logic of good_mux is realized in terms of standard cell gates available in the **sky130_fd_sc_hd__tt_025C_1v80.lib** library.

Generate netlist:

```
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

![abc](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/3b297d30-2e31-4170-a4ef-6569682c311f)


It also infers number of inputs and outputs in the design.


**show command:**

It is  used to see the logic the synthesizer has realized.It will show the graphical version of logic it has realized.

```
show
```


</details>

## Day 2
<details> <summary> Introduction to timing.libs:

</summary>

To view the contents present in the library file,give the following commands:

```
gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```





</details>

