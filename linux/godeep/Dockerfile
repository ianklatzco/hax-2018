# docker run -d -p 6969:22 godeep
FROM ubuntu:latest

RUN apt-get update 

COPY flag.txt /root/Xd73dew.txt
COPY make_dir.sh /home/godeep/

RUN /home/godeep/make_dir.sh
RUN cp /root/Xd73dew.txt /home/godeep/1/2/3/4/5/6/7/8/9/10/11/12/13/14/15/16/17/18/19/20/21/22/23/24/25/26/27/28/29/30/31/32/33/34/35/36/37/38/39/40/41/42/43/44/45/46/47/48/49/50/51/52/53/54/55/56/57/58/59/60/61/62/63/64/65/66/67/68/69/70/71/72/73/74/75/76/77/78/79/80/81/82/83/84/85/86/87/88/89/90/91/92/93/94/95/96/97/98/99/100/101/102/103/104/105/106/107/108/109/110/111/112/113/114/115/116/117/118/119/120/121/122/123/124/125/126/127/128/129/130/131/132/133/134/135/136/137/138/139/140/141/142/143/144/145/146/147/148/149/150/151/152/153/154/155/156/157/158/159/160/161/162/163/164/165/166/167/168/169/170/171/172/173/174/175/176/177/178/

# make everything 755
# rwx r-x r-x
# ^ owner
#     ^group
#         ^everyone
# 644 rw- r-- r--
RUN find /home/godeep/1 -type f -exec chmod 644 {} + && find /home/godeep/1 -type d -exec chmod 755 {} +

RUN rm /root/Xd73dew.txt
RUN rm /home/godeep/make_dir.sh

# might need to be ENTRYPOINT
# CMD tail -f /dev/null

# ssh service
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
# create a root password
RUN echo 'root:sD5YkuJ1^h3RPvE%' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

