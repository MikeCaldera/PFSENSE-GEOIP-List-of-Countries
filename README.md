- 👋 Hi, I’m @MikeCaldera
- 👀 I’m interested in helping others
- 🌱 I’m currently learning everything again
- 💞️ I’m looking to collaborate on linux security
- 📫 How to reach me mikecaldera at yahoo
- 😺 paypal Donation mikecaldera at yahoo . com

Use this code to save time by adding a alternative GEO IP lIST other than PFBlocker. This is absolutely free! However, some people don't want their data sold to third parties so here's an alternative freeware list. Big thanks to  [IPdeny](https://www.ipdeny.com/ipblocks/
)
This was a PITA time consuming task to do. I could of wrote a bot in the same time it took but it's done now. Now you will always get the lastests IP addresses. Don't pull this request multiple times daily but rather weekly. This code could be used to block traffic or allow traffic to those countries listed above. All I did was save you hours of time. You must add these rules as need into your firewall rules. Remember, by default PFSense blocks all traffic into the WAN so you could just say Allow In to USA only. Whatever floats your boat. Just use Drop for Wan and Reject for Lan. 

WARNING - BACKUP your firewall in pfsense first before you do anything!! You should always have backups saved locally so don't blame me if you Bork your PFsense. Also,any Firewall Aliases URLs lists will be overwritten... unless you copy and paste this code along with your existing Firewall Aliases URLs. Ok so now that's out of the way

1) in the web gui go to-> Diagnostics/Backup & Restore/Backup & Restore then download configuration as XML save as old firmware.

2) **Make a new copy but this time call it new firmware but make sure its not the same name. You should have two files. One is the orginal untouched backup xml. The new xml file we are going to insert this code into the exact placement and save it.**

3) Double check your new code and make absolutely certain you placed it in the correct spot. Save it then upload it to your pfsense.

4) Once pfsense takes the upload go into     Firewall/Aliases/URLs and hopefully you have the entire geolist. You may have to reboot pfsense for changes to take effect.

5) The URL rules are NOT ACTIVE until you make it active by adding into your WAN to ALLOW IN lets say USA is allowed in but everything else we wont respond. LAN rules you could Block the following countries in Both directions both in and out. It's up to you. Hopefully this helped you save time and money. 



