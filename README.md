# OSCP File Transfer Tool

  

This repository provides a streamlined solution for file transfers during the OSCP exam using various protocols, including FTP, PUT, and SMB.

  

## Installation

  

1. Clone the Repository:

```
$ git clone https://github.com/Bit-ByteBandit/OSCP-FIleTransfer.git
```

2. Navigate to the Directory:

```
$ cd OSCP-FIleTransfer
```

3. Install Dependencies:

```
$ python3 -m pip install -r requirements.txt
```

## Usage

  

The tool offers flexible transfer methods and customizable options:

```
python3 oscp-transfer.py -m {METHOD} [options]
```

Options:

  

- -h, --help: Display the help message and exit.

- -m {PUT, FTP, SMB, GET}: Choose the transfer method.

- -l PORT: Specify the listening port (default: 21 for FTP).

- -d DIRECTORY: For FTP or SMB, set the working directory (default: SHARE for SMB).

- -u USERNAME: Provide the FTP or smb username (default for ftp only: user).

- -p PASSWORD: Provide the FTP or smb password (default for ftp only: user).

  

Examples:

  

- Initiate a GET server on port 80:

```
python3 oscp-transfer.py -m GET -l 80
```

- Initiate a PUT server on port 80:

```
python3 oscp-transfer.py -m PUT -l 80
```

- Use FTP with custom options:

```
python3 oscp-transfer.py -m ftp -l 21 -d /path/to/directory -u username -p password
```

- Use SMB with a specific directory:

```
python3 oscp-transfer.py -m smb -u foo -p foo -sh MySharefoo -smb2
```

## Running Servers

  

Start GET-HTTP Server:

```
python3 oscp-transfer.py -m GET
```

Start SMB Server:

```
python3 oscp-transfer.py -m SMB
```

Start FTP Server:

```
python3 oscp-transfer.py -m FTP
```

Start PUT-HTTP Server:

```
python3 oscp-transfer.py -m PUT
```
Upload a file using **PUT** request:

```
curl http://[IP] -T [File]
```
