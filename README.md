- 👋 Hi, I’m @MikeCaldera
- 👀 I’m interested in helping others
- 🌱 I’m currently learning everything again
- 💞️ I’m looking to collaborate on linux security
- 📫 How to reach me mikecaldera at yahoo
- 😺 paypal Donation mikecaldera at yahoo . com

Use this code to save time by adding a alternative GEO IP LIST other than PFBlocker. This is absolutely free! However, some people don't want their data sold to third parties so here's an alternative freeware list. Big thanks to  [IPdeny](https://www.ipdeny.com/ipblocks/
)
This was a PITA time consuming task to do. I could of wrote a bot in the same time it took but it's done now. Now you will always get the lastests IP addresses. Don't pull this request multiple times daily but rather weekly. This code could be used to block traffic or allow traffic to those countries listed above. All I did was save you hours of time. You must add these rules as need into your firewall rules see image (https://github.com/MikeCaldera/PFSENSE-GEOIP-List-of-Countries/blob/main/paste%20here.png). Remember, by default PFSense blocks all traffic into the WAN so you could just say Allow In to USA only. Whatever floats your boat. Just use Drop for Wan and Reject for Lan. 

WARNING - BACKUP your firewall in pfsense first before you do anything!! You should always have backups saved locally so don't blame me if you Bork your PFsense. Also,any Firewall Aliases URLs lists will be overwritten... unless you copy and paste this code along with your existing Firewall Aliases URLs. Ok so now that's out of the way

1) in the web gui go to-> Diagnostics/Backup & Restore/Backup & Restore then download configuration as XML save as old firmware.

2) **Make a new copy but this time call it new firmware but make sure its not the same name. You should have two files. One is the orginal untouched backup xml. The new xml file we are going to insert this code into the exact placement and save it.**

3) Double check your new code and make absolutely certain you placed it in the correct spot. see location to paste in this image ("https://github.com/MikeCaldera/PFSENSE-GEOIP-List-of-Countries/blob/main/paste%20here.png") Save it then upload it to your pfsense. 

4) Once pfsense takes the upload go into Firewall/Aliases/URLs and hopefully you'll have the entire geolist. You may have to reboot/reload rules pfsense for changes to take effect. https://github.com/MikeCaldera/PFSENSE-GEOIP-List-of-Countries/blob/main/sample_URL_Aliase_Countries_Block_List.png

5) The URL rules are NOT ACTIVE until you make it active by adding into your WAN to ALLOW IN lets say USA is allowed in but everything else we wont respond. LAN rules you could Block the following countries in Both directions both in and out. It's up to you. Hopefully this helped you save time and money. 

https://www.ipdeny.com/ipblocks/data/aggregated/

<------------------------------------------------------------------------------------------------------------------------->
UPDATE JAN 11, 2023 - For large numbers of entries, use a "URL Table type alias" which is capable of handling larger lists. Cange each country list to this type.

IPDENY now has consolidated the list of IPS so that your router won't skip these ips due to the larger size. No need to download these files directly on your router unless you have large RAM installed. You will also have to adjust the     System/Advanced/Firewall & NAT -Packet Processing
"Firewall Maximum Table Entries" to a much larger number than your firewall can handle. I use 1.6 million with 32 gigs Ram

https://www.ipdeny.com/ipblocks/data/aggregated/us-aggregated.zone

Example: the USA list had over 64,000 cidr entries UNITED STATES (US) [download us.zone] Size: 985.86 KB (64080 IP blocks)
do not use [download us.zone] instead use [download us-aggregrated.zone] (23090 IP blocks)

Using the AGGREGATED ZONE has a better performance and less slippage of IPS creeping through your firewall tables. 

