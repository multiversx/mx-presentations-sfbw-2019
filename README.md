# San Francisco Blockchain Week 2019 Workshop

## Part 1: become a validator on a sandboxed Elrond Testnet:
### Become a validator when running a linux OS:
```
sudo apt-get install git -y
git clone https://github.com/ElrondNetwork/elrond-go-scripts --single-branch --branch sf2019
cd elrond-go-scripts/ubuntu-amd64/
./install.sh
```

### Become a validator when running a Mac OS:
```
git clone https://github.com/ElrondNetwork/elrond-go-scripts --single-branch --branch sf2019
cd elrond-go-scripts/darwin-amd64/
./install.sh
```

When prompted to enter a name just add a custom string and then you can start the node by choosing the option `front`
The credentials are generated automatically and, by default, each new node will join the network as observer on shard 0. 


### What the install.sh script does

The following script lines download a github repo containing bash script that does the following:
1. Install prerequisites like git, curl and wget (if missing);
1. Download from https://github.com/ElrondNetwork/elrond-go/releases/tag/sf2019-1 required tar.gz archive file that contains the following binaries: 
      - node - the elrond-go node binary;
      - keygenerator - a simple tool to generate cryptographic credentials;
      - libwasmer_runtime_c_api binary used by the Arwen VM.
1. The script also clones a config repo from here: https://github.com/ElrondNetwork/elrond-config/tree/sf2019 that contain all required config files for the node binary to connect to the rest of the network;
1. Please note that libwasmer_runtime_c_api binary si copied in /usr/lib (or /usr/local/lib in Mac OS) so that operation requires elevation.

###


## Part 2: Developing SmartContracts:

1) Download and install VSCode from here: https://code.visualstudio.com/download

2) Download latest released VSIX file (Visual Studio Code extension):
https://github.com/ElrondNetwork/vscode-elrond-c/releases/

3) Install VSIX file in vscode.
`Ctrl+Shift+P`, command `Install from VSIX`. Select the downloaded VSIX file. Install, restart vscode.

![](images/003_install_extension.png)

4) Adjust settings: `Ctrl+Shift+P`, command `open settings (UI)`. Search for `elrond*` settings. They are as follows:

- Elrond - download mirror: `https://workshop.elrond.com/ElrondIDE`
- **Elrond - IDE folder**: `/home/someone/Elrond/ide`
- Elrond - rest api port: `8080`
- Elrond - testnet URL: `https://wallet-workshop.elrond.com`

**You only need to set `Elrond - IDE folder`. Note that dependencies will be downloaded to this folder.** 

![](images/004_adjust_settings.png)

5) In Visual Studio Code, open a folder (workspace). This is where development of smart contracts will take place. `Ctrl+Shift+P`, command `Open Folder`.

6) Open **Elrond IDE**: `Ctrl+Shift+P`, command `Elrond - open IDE`.

![](images/006_open_IDE.png)

5) Go to tab "Environment", install dependencies (automatically):
- A part of LLVM suite (clang, llc, wasm-ld).
- "elrdon-do-node-debug": https://github.com/ElrondNetwork/elrond-go-node-debug
- Golang build chain, required to build "elrond-go-node-debug".All these will be installed in the configured IDE folder.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/005%20-%20setup%20environment.png)

6) Go to "Home" tab. Hit "Refresh" to list the .c smart contracts in the workspace.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/006%20-%20refresh%20list%20of%20contracts.png)

7) Hit "Build" to obtain the WASM bytecode.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/007%20-%20build%20bytecode.png)

8) Go to "Build output" to inspect the logs.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/008%20-%20build%20output.png)

9) Start node-debug.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/009%20-%20start%20node-debug.png)

10) Deploy the smart contract on node-debug.
![]()

11) Inspect the address of the smart contract.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/011%20-%20see%20scAddress.png)

12) Inspect the output of node-debug.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/012%20-%20node-debug%20output.png)

13) Inspect the REST dialogue between the vscode extension and the HTTP endpoint of node-debug.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/013%20-%20rest%20dialogue.png)

14) Run a function exported by the smart contract.

15) Inspect the output (vmOutput) of run.

16) Start a node on the testnet.
./node
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/016%20-%20start%20node%20on%20testnet.png)

17) Hit "deploy on testnet" and choose the appropriate private key file. Then hit "deploy".
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/017%20%20-%20deploy%20on%20testnet.png)

18) Inspect the address of the smart contract.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/018%20-%20see%20scAddress.png)

19) Run a function on the testnet. Don't forget to choose the appropriate private key file.
![](https://github.com/ElrondNetwork/sfbw2019/blob/master/images/019%20-%20run%20on%20testnet.png)

20) Inspect balance of the account that ran the function.
Open testnet explorer and check account balance
