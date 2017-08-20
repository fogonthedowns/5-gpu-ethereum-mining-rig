# ETHEREUM MINING

### 5 GPU Ethereum Mining Rig Build Guide - (8-16 hours of work)

![Image of 5 GPU RIG](https://github.com/fogonthedowns/5-gpu-ethereum-mining-rig/blob/master/images/5gpu_rig.png)

#### Power Supply 

 * [1200 Watt Power Supply](https://jet.com/product/HXi-Series-HX1200i-High-Performance-ATX-Power-Supply/e525fd4b59e34b1fbe0cca46c412941b)

#### Motherboard/CPU 

 * [MSI Pro Z170A SLI Plus Motherboard](https://jet.com/product/MSI-Desktop-Motherboard-Intel-Z170-Chipset-Socket-H4-LGA-1151-Z170A-PC-MATE/1fda8cbd10554b028bd7be07a44f9b41) |  [Intel G3900 Dual Core CPU](https://jet.com/product/Intel-Intel-Celeron-G3900-Skylake-Dual-Core-28-GHz-LGA-1151-65W-BX80662G3900-Des/57f74c89a7564b81914acb7afb723589)
￼
#### GPUs 

 * 5x Graphics Cards (GPUs) – [Nvidia GTX 1070](https://jet.com/product/ASUS-ROG-Strix-GeForce-GTX-1070-8GB-Gaming-Card/8ce8d8f42a9446eba44c80b4120395e8) – The efficient Nvidia GTX 1070 can produce 25Mh/s using only 150 watts of electricity.

![Image 140 MH/s](https://github.com/fogonthedowns/5-gpu-ethereum-mining-rig/blob/master/images/140%20Mh:s.png)

#### RAM

 * RAM (System Memory) –  4 GB RAM – You don’t need a lot of system memory to mine ethereum effectively.

#### GPU cables

 * [USB Riser Cables](https://www.amazon.com/MintCell-6-Pack-Powered-Adapter-Extension/dp/B01GU94QSQ/ref=pd_lpo_vtph_147_bs_t_1?_encoding=UTF8&psc=1&refRID=D0HP0K39ZVGXD997G2YN) –  (5 pack) USB Riser Cables – Used to connect the 5 graphics cards to the motherboard and allow spacing between cards for heat dissipation. These are necessary when building a rig with this many GPU’s.

#### Hard Disk

 * 1x Hard Drive (SSD)  –  Solid State Drive  for installing operating system and your mining software.

#### Rig Case

 * 1x Custom Mining Case –  I’d recommend an Open Air 5 GPU Mining Case.I’ve built several of these 5 GPU rigs for family and friends using this particular mining case works quite well for airflow and ease of building.

#### On/Off Switch

 * [Power Button](https://www.amazon.com/gp/product/B01FM62DTC/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1)

#### Other stuff

 * Keyboard/Mouse/HDMI cable for montior
 * 8GB USB stick
 * [usb wifi adaptor ](https://www.amazon.com/gp/product/B00EQT0YK2/ref=oh_aui_detailpage_o05_s00?ie=UTF8&psc=1)


# Build Guide 

1. Un-package everything
2. Build / assemble Open Air 5 GPU Mining Case
3. Install processor and RAM on motherboard
4. Plug in all riser cables
5. Place motherboard in custom open air mining rig case and connect motherboard PSU connector (leaving PSU unplugged from the wall of course)
6. Plug in SATA hard drive (or optional Linux on USB stick)
7. Connect all GPUs to riser cables and fasten them to custom case. You might need to experiment for optimal spacing to keep the cards cool.
8. Plug in all power supply connections.
9. Connect mouse, monitor and keyboard and an internet connection (I use a USB WiFi adapter)
10. Check all connections once more
11. Fire it up! Install Ubuntu 16.04
12. Make sure fans are fully functional. Start the mining software, tweak settings for maximum hash rates and let it run!
Motherboard, Windows and Mining Software Configuration
1. Update the motherboard to the latest BIOS using a USB thumb drive. You can find the latest BIOS for the Z170 SLI Plus motherboard here.
2. Configure Motherboard BIOS with the following settings changes:
    * Settings > Advanced > PCI subsystem Setting: PEG 0 and PEG 1 set to Gen1
    * Above 4G Decoding (cryptocurrency mining) should be set to Enabled
    * Save and reboot

### Install OS

 * [Download Ubuntu 16.04](https://help.ubuntu.com/community/InstallCDCustomization)
 * If you are on a mac, create bootable USB with these [instructions](http://osxdaily.com/2015/06/05/copy-iso-to-usb-drive-mac-os-x-command/)
 * boot your system type `delete` rappidly to enter BIOS mode. Toggle boot order to boot from USB. Save and restart.


#### OS extras:

 * open terminal:
 ```
 sudo apt install git
 sudo apt-get update
 sudo apt-get install vim
 ```

### Update Bios

1. [Download bios update](https://us.msi.com/Motherboard/support/Z170A-PC-MATE.html#support_download)
2. Move file to USB drive
3. restart computer, press `delete` to enter bios mode
4. Select `M-Flash` to update from USB drive


### install cuda

exit ubuntu gui:
`ctl` + `alt` + `f1`

stop ubuntu GUI:
```
sudo service lightdm stop
sudo init 3
```
Nvidia Cuda drivers [https://developer.nvidia.com/cuda-downloads]
```
sudo sh [NVIDIA .run file]
```
be sure to set PATH variables as noted by the output. Add to the `PATH` of `.bashrc`:
```
sudo vi ~/.bashrc
PATH="/some/new/path:$PATH"
```
save. exit. and source the environment variables: `source ~/.bashrc`

Next, enter `sudo init 5`. And restart your system with `sudo restart`

```
sudo apt-get purge nvidia*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
sudo apt-get install nvidia-367
```
### restart your system

```
nvidia-smi
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 375.82                 Driver Version: 375.82                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce GTX 1070    Off  | 0000:01:00.0      On |                  N/A |
| 29%   57C    P2    47W / 151W |   2483MiB /  8113MiB |     95%      Default |
+-------------------------------+----------------------+----------------------+
|   1  GeForce GTX 1070    Off  | 0000:04:00.0     Off |                  N/A |
| 45%   72C    P2   111W / 151W |   2220MiB /  8114MiB |     48%      Default |
+-------------------------------+----------------------+----------------------+
|   2  GeForce GTX 1070    Off  | 0000:05:00.0     Off |                  N/A |
| 41%   68C    P2    60W / 151W |   2220MiB /  8114MiB |     24%      Default |
+-------------------------------+----------------------+----------------------+
|   3  GeForce GTX 1070    Off  | 0000:06:00.0     Off |                  N/A |
| 40%   68C    P2   106W / 151W |   2220MiB /  8114MiB |     36%      Default |
+-------------------------------+----------------------+----------------------+
|   4  GeForce GTX 1070    Off  | 0000:07:00.0     Off |                  N/A |
| 45%   70C    P2   122W / 151W |   2220MiB /  8114MiB |     28%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID  Type  Process name                               Usage      |
|=============================================================================|
|    0      1187    G   /usr/lib/xorg/Xorg                             157MiB |
|    0      2058    G   compiz                                         104MiB |
|    0      2700    C   ethminer                                      2217MiB |
|    1      2700    C   ethminer                                      2217MiB |
|    2      2700    C   ethminer                                      2217MiB |
|    3      2700    C   ethminer                                      2217MiB |
|    4      2700    C   ethminer                                      2217MiB |
+-----------------------------------------------------------------------------+
```

or 

```
watch -n0 nvidia-smi
```

### Ethminer

Download [Ethminer](https://github.com/ethereum-mining/ethminer#build)
```
mkdir build; cd build
cmake .. -DETHASHCUDA=ON -DETHASHCL=OFF
cmake --build .
sudo make install
```

At this point you could start mining. This is the command to do so. Notice you must fill in your wallet address and your worker name. I've decided to use [Dwarfpool](https://dwarfpool.com/eth) because I like the name and it works for me. However there are many [other](https://www.buybitcoinworldwide.com/ethereum/mining-pools/) mining pools. If you need a wallet you can download [mist](https://github.com/ethereum/mist/releases) to make one.

```
/bin/ethminer -G -F http://eth-us2.dwarfpool.com/[YOUR_WALLET_ADDRESS]/[YOUR_WORKER]
```

If you decide to proxy through stratum use the information above as a reference for edits you will make to `eth-proxy.conf` in the eth-proxy instructions.


### Eth-Proxy

Stratum Proxy v0.0.5 offers an additional 10-20% increase of earning compared to standard getwork and failover option

```
   Pool A (e.g. dwarfpool) <---+                         +------ (ethminer process) ----+ NVIDIA 1070 0
 (Active)                      |                         |
                               |                         +------ (ethminer process) ----+ NVIDIA 1070 1
                               |                         |
  Pool B  <--------------------+---- StratumProxy  <-----+------ (ethminer process) ----+ NVIDIA 1070 2
(Dwarfpool FailOver)                                     |
                                                         +------ (ethminer process) ----+ NVIDIA 1070 3
                                                         |
                                                         +------ (ethminer process) ----+ NVIDIA 1070 4
```


 * Download [eth-proxy](https://github.com/Atrides/eth-proxy)
 * `apt-get install python-twisted`
 * Edit `eth-proxy.conf` with your wallet id, and [dwarfpool](https://dwarfpool.com/eth/) uris
 * Start Ethproxy: `python ./eth-proxy.py`

In my case the build is in cpp-thereum-master directory Run:

```
/bin/ethminer --farm-recheck 200 -G -F http://127.0.0.1:8080/rig1
```


### Troubleshooting

#### Login-Loop:

 * If you get stuck in the Ubuntu Login loop checkout `x-session-errors.log` accessible through [answer 2](https://askubuntu.com/questions/223501/ubuntu-gets-stuck-in-a-login-loop)
 

