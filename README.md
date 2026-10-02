VS Code Remote SSH Setup

This guide explains how to connect to the remote server using **Visual Studio Code** and the **Remote - SSH** extension.

# VS Code Remote SSH Setup

This guide explains how to connect to a remote Linux server using **Visual Studio Code** and the **Remote - SSH** extension.

---

## Prerequisites

Before starting, make sure you have:

- Visual Studio Code installed
- SSH access to the remote server
- The server IP address
- Your SSH username and password

Example:

| Parameter | Value |
|-----------|-------|
| Host | `...` |
| Username | `...` |

---

## Step 1 - Install Visual Studio Code

Download Visual Studio Code from:

https://code.visualstudio.com/

Install it using:

```bash
sudo dpkg -i code_*.deb
```

## Step 2 - Install the Remote - SSH Extension

1. Open **Visual Studio Code**.
2. Open the **Extensions** tab (`Ctrl + Shift + X`).
3. Search for:

```
Remote - SSH
```

4. Install the extension published by **Microsoft**.

---

## Step 3 - Configure SSH

Open a terminal on your local machine and edit (or create) the SSH configuration file:

```bash
nano ~/.ssh/config
```

Add the following configuration:

```text
Host ...
    HostName ...
    User ...
```

Save the file and exit (`Ctrl + O`, `Enter`, `Ctrl + X`).

---

## Step 4 - Connect to the Remote Server

Inside VS Code press:

```
Ctrl + Shift + P
```

Search for:

```
Remote-SSH: Connect to Host...
```

Select:

```
(...)
```

If prompted for the operating system, select:

```
Linux
```

Enter your SSH password.

After a successful connection, the bottom-left corner of VS Code should display:

```
SSH: (...)
```

---

## Step 5 - Open Your Project

Go to:

```
File → Open Folder...
```

Navigate to your project folder on the remote server.

Example:

```text
/home/km3user1/efthimis/...
```

Click **Open**.

If VS Code asks whether you trust the authors, select:

```
Yes, I trust the authors
```

---

## Step 6 - Open a Remote Terminal

Open a terminal:

```
Terminal → New Terminal
```

or press:

```
Ctrl + Shift + `
```

This terminal is running **on the remote server**, not on your local computer.

Verify the connection:

```bash
hostname
pwd
```

---

## Step 7 - Basic Linux Navigation

Display the current directory:

```bash
pwd
```

List files:

```bash
ls
```

List all files (including hidden):

```bash
ls -la
```

Move into a directory:

```bash
cd folder_name
```

Move back one directory:

```bash
cd ..
```

Go to your home directory:

```bash
cd ~
```

---

## Step 8 - Open Files

Open a file in the VS Code editor:

```bash
code filename.py
```

Example:

```bash
code train.py
```

Open the current directory:

```bash
code .
```

---

## Step 9 - Run Python Scripts

Activate your Python environment if required.

For a Conda environment:

```bash
conda activate drakopoulou
```

For a virtual environment:

```bash
source /path/to/environment/bin/activate
```

Run a Python script:

```bash
python3 filename.py
```


Stop execution with:

```
Ctrl + C
```

Deactivate the environment when finished:

```bash
conda deactivate
```

or

```bash
deactivate
```

---

## Step 10 - Disconnect

Click the green SSH indicator in the bottom-left corner:

```
SSH: (...)
```

Select:

```
Close Remote Connection
```

---

## Typical Workflow

1. Open VS Code.
2. Connect to the remote host using **Remote-SSH**.
3. Open your project folder.
4. Open a terminal.
5. Activate your Python environment.
6. Run your Python scripts.
7. Edit files directly on the remote server.
8. Disconnect when your work is complete.

---

## Notes

- All files remain on the remote server.
- Code is executed on the remote machine.
- The local computer is only used as the development interface.
- The remote server's CPU, GPU, Python installation and libraries are used during execution.
- Once configured, reconnecting only requires selecting the host from **Remote-SSH: Connect to Host**.

