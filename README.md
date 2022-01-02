# pfsense-pihole-backup

## Quick setup
Use a cronjob for this, and run it as often as you would like.
```bash
git clone https://gitea.perfectra1n.com/perf3ct/pfsense-pihole-backup.git
cd pfsense-pihole-backup/
pip install -r requirements.txt
```

You can then run the `main.py` as often as you would like, and setup the Pihole / pfSense output locations using the flags shown below.
If your password contains any special characters, be sure to prepend the special character with a backslash: `\` when calling the script from the command line
Example useage:
```bash
python main.py ~/.ssh/sshkey.pem --pihole 192.168.1.2 --user perf3ct --pihole-password Password123
```

## Help Output:
```bash
[root@DESKTOP-ORG3A01] ~/repos/pfsense-pihole-backup
 > python main.py -h                                                                                                 
usage: main.py [-h] (--pfsense PFSENSE | --pihole PIHOLE) [--user USER] [--pfsense-output PFSENSE_OUTPUT] [--pihole-output PIHOLE_OUTPUT] [--pihole-password PIHOLE_PASSWORD] [--debug] private_key

This is the description for the main parser!

positional arguments:
  private_key           Required. Please provide the path to your private key to be used to SSH into pfSense.

optional arguments:
  -h, --help            show this help message and exit
  --pfsense PFSENSE     Provide the IP address / hostname of PfSense that you wish to fetch the config of.
  --pihole PIHOLE       Provide the IP address / hostname of Pihole that you wish to fetch the config of.
  --user USER           Required. Provide the username to connect as.
  --pfsense-output PFSENSE_OUTPUT
                        Optional. Provide the output name of the pfsense config file.
  --pihole-output PIHOLE_OUTPUT
                        Optional. Provide the output name of the PiHole config file.
  --pihole-password PIHOLE_PASSWORD
                        Optional. Provide the password for your PiHole installation so that the config package can be generated.
  --debug               Optional. Use this argument if you are debugging any errors.
```