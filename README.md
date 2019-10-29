# San Francisco Blockchain Week 2019 Workshop

## Part 1: become a validator on a sandboxed Elrond Testnet:

The following script lines download a github repo containing bash script that does the following:
1. Install prerequisites like git, curl and wget (if missing);
1. Download from https://github.com/ElrondNetwork/elrond-go/releases/tag/sf2019-1 required tar.gz archive file that contains the following binaries: 
      - node - the elrond-go node binary;
      - keygenerator - a simple tool to generate cryptographic credentials;
      - libwasmer_runtime_c_api binary used by the Arwen VM.
1. The script also clones a config repo from here: https://github.com/ElrondNetwork/elrond-config/tree/sf2019 that contain all required config files for the node binary to connect to the rest of the network;
1. Please note that libwasmer_runtime_c_api binary si copied in /usr/lib (or /usr/local/lib in Mac OS) so that operation requires elevation.

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

## Part 2: xxxxxx:
