## ASIC




## Day 0
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

 ## Day1 

<details><summary>Introduction to verilog RTL Design and Synthesis</summary>

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
<details> <summary> Introduction to timing.libs

</summary>


**.lib files:**


To view the contents present in the library file,give the following commands:

```
gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

**sky130_fd_sc_hd__tt_025C_1v80:**

*sky denotes skywater,the name of library.*

*tt denotes typical(libraries can be fast slow typical).*

*025C denotes temperature.*

*1v80 denotes voltage.*


![lib](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/727802ee-c8f1-4c90-8719-fdc2d8d1a5fc)

There are three very important parameters which have have to be taken into consideration seriously for the design to work desirably:

1.Process

2.Voltage 

3.Temparature



**Process:**

This refers to the natural variability that occurs during the semiconductor manufacturing process. Process variation can lead to differences in transistor performance, gate delays, and other electrical properties.

**Voltage:**

Voltage variations or supply voltage fluctuations can impact the performance of digital circuits. If the supply voltage deviates from the expected value, it can affect the threshold voltages of transistors, leading to changes in the propagation delays and power consumption of the circuit.


**Temaparature:**

Temperature variations can also influence the behavior of digital circuits. Higher temperatures can cause transistors to become more leaky, leading to increased power consumption and potentially affecting the timing behavior of the circuit.


Our libraries will be characterized to model these **PVT** variations.

**.lib is a  bucket of all the standard cells**.So to highlight the begining of the cell definition use the below keyword:

```
:se hls
```


![cell highlight ](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/d0e761ff-a10d-4479-a40e-5e7f1c017667)


To see the different flavours of the same cells and different cells:

```
:g//
```



![diff cells](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/cf777ebd-5466-4680-839d-dbf0ddd26376)



To understand the functionality:

.lib is going to contain different features of cell.To understand the characteristics of the cell we can look at the equivalent verilog model.

Proceed with the following keyword in the library file:

```
sp ../my_lib/verilog_model/sky130_fd_sc_hd.v
```


![Features of cells](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/ab9175bc-8916-47a7-b74e-c9740ddad546)

You can infer that .lib contains information about area number,leakage power,powerport.

It also describes each input combination,i.e., 32 combinations for 5 inputs:

![Screenshot from 2023-08-12 23-52-35](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/6917ed42-2859-4182-ade6-e2bda174566e)


>The input capacitance of the pin.

>The power related to that input pin.

>the transition related to that pin.

>The delay related to that pin.



</details>

<details> <summary>Hierarchical Synthesis vs Flat Synthesis</summary>


**Hierarchiacal Synthesis:**
It refers to a design methodology where a complex digital circuit is created by breaking it down into smaller, more manageable modules or blocks. Each module is designed and synthesized separately, and then these modules are integrated hierarchically to create the complete circuit.


**Example:**

To get a better understanding of this hierarchical synthesis we shall synthesize a design file named multiple modules.


**Multiples Modules:**

To view the file move to the verilog_file directory:

```
cd VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files/
gvim multiple_modules.v
```
![multiple module](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/4b2b5f3c-0a7a-4d69-92ea-8f39df7dbb6e)



From the verilog file what we realize is the image shown below :

![multiple modules 1](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/2b6ce52a-258a-43e6-a05b-1b55047b70a3)


Now lets synthesize the verilog file using yosys,

To synthesize:

```
yosys
read_verilog multiple_modules.v
synth -top multiple_modules
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
show multiple_modules 
```
*since there are several modules present specify the name along with the show command.*



![yosys show](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/3a09410c-ca34-4a37-873f-fd7dfb2251f8)




Now from the image you can clearly see that it is not showing **and** and **or** gate.It is showing u1 and u2 instances of submodule1 and submodule2.This is called as the hierarchical design.

Now we shall write out the netlist and see how the netlist looks like,

```
write_verilog multiple_modules_hier.v
!gvim multiple_modules_hier.v
```

![netlist](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/ee5ef68a-9b8f-4909-8c91-b048ee7f309d)


In submodule2 we are expecting an or gate but what happening in yosys synthesis is shown in the below image:



![Nand nor](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/68093c8a-f5ff-42a6-90c6-61fc96bd8f0e)

As we can infer from the above image the yosys synhtesize a nand logic.The nand logic contains a stacked nmos where as nor logic contains stacked pmos.The stacked pmos is always bad because the pmos has poor mobility. To improve this we have to make this cell really a wide cell to get good logical circuit which requires more area.This can impact the overall chip area and potentially reduce the number of gates that can be integrated onto a chip.


**Flat Synthesis:**
It is the opposite of hierarchical synthesis in the context of digital design, particularly in RTL (Register Transfer Level) design. While hierarchical synthesis involves breaking down a complex design into smaller modules and then integrating them hierarchically, flat synthesis refers to synthesizing the entire design as a single, monolithic unit without using hierarchical module decomposition.

To view the netlist for the flattened synthesis:

```
write_verilog -noattr multiple_modules_flat.v
gvim multiple_modules_flat.v
```


![Flatten](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/2ee50214-ff14-4c55-9b48-80c06ee1adf8)

![flat show](https://github.com/IIITB-ARUL/IIITB-MT2023529/assets/140998631/23ab7929-a5dc-4d2f-882c-59509f6f2d7e)



You can infer from the image that it has single netlist.The hierarchies are flattened out.We candirectly see the instantiation of and and or gates.

**Synthesization of submodules:**

To synthesise submodule:


```

yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
read_verilog 
read_verilog multiple_modules.v 
synth -top sub_module1
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
```

**Why submodule level synth?**

1.When have multiple instances of same module we can synthesise it one time and replicate it multiple times and stitch it together in the top module.

2.**Divide and Conquer:** When we give massive design to a tool,the tool may not be doing a good job.Instead we give portions of the massive design so a nice netlist is written out and synthesizedand finally stitched together in the topmodul.

