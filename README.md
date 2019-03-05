# autossh-tunnel-windows

## Setup

1. Install Cygwin64 for Windows: https://www.cygwin.com/ (**alternatively, you could possibly use the Linux Subsystem for Windows now for Win 10+, but I've not tried this**).
2. Enable `AutoSSH` module in Cygwin: https://support.chartio.com/docs/data-sources/autossh-windows.
3. Copy the `.ssh/` folder to your Windows user directory (e.g. `C:\Users\<USERNAME>\.ssh`)
4. Create your SSH public/private key pair (https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ssh-from-windows). Ensure the private key is saved as `C:\Users\<USERNAME>\.ssh\id_rsa`, and the public key is saved as: `C:\Users\<USERNAME>\.ssh\id_rsa.pub`.
5. Modify the SSH config file using the example `C:\Users\<USERNAME>\.ssh\config`, to setup your port forwarding tunnels and hosts.
6. Copy your **public SSH key** to the server you wish to connect to via SSH. **The private key remains on your local computer only.**
7. Install the Non-Sucking Service Manager (NSSM) for Windows: https://nssm.cc/download to the following location: `C:\Program Files\nssm-2.24\win64\nssm.exe`.
8. Copy the `Autossh` folder to `C:\Users\<USERNAME>\Autossh`.
9. Run the `C:\Users\<USERNAME>\Autossh\nssm-install-autossh.bat` file as an Administrator. When prompted to choose the executable, select `C:\Users\<USERNAME>\Autossh\run-autossh.bat`. Also, enter a name for the new service.
10. You should now find the service in the `services.msc` dialog. Change the startup type to `Automatic (delayed)` and test!