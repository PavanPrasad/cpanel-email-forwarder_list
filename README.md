# cpanel-email-forwarder_list
#Script to list the email forwarders in WHM/cPanel
#!/bin/bash
#####Description: Script for fetching the complete email forwarder list####
####Author: PAVAN PRASAD####
####Created on: 08/10/2020###
cat /etc/userdatadomains| awk -F':' '{print $1}' > domainlist
cd /etc/valiases
>output.txt
for i in `cat /root/work/domainlist`;do
#echo $i >> output.txt
cat "$i" | grep -v "*" >> /root/work/output.txt
echo "" >> /root/work/output.txt
done
#cp -a /root/work/output.txt /root/work/out1.txt
#sed -i 's/:/;/g' out1.txt
#sed -i 's/,/;/g' out1.txt
