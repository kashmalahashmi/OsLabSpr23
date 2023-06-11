Installing squid
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/b6e42297-c8b5-4679-998c-28c5d494432b)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/fd52fa25-390a-4c9a-a072-0672c5e7461e)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/f56435c3-cbe7-48bb-8d95-e5690aba450b)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/d7f998d5-622e-483a-a720-6126646621cf)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/3efcac92-ade5-4e80-be13-827d7ad19cdf)

Listing services

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/e4406016-5d2b-447c-a6cd-5e61bcb98b3d)

Setting up unattended upgrades
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/0cfc934a-3aef-48ed-a787-ef80cc533143)


Staying up to date
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/b4885256-80d5-421d-bb15-0e1bdb952e27)

Updating the Kernel

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/dc9d84de-116e-40a2-b8fc-4088c0747cfb)

Setting up ufw
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/fe5882a1-e0f0-4294-bf0c-2ec199966701)

ufw allowing http and https only

nftables

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/303dea65-d12a-4415-8429-f4ee291612fe)

Configuring nftables
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/db5e22e9-27b9-4968-8003-6e4495485889)

Listing nft ruleset
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/5d055586-ac1a-42d1-845f-5c44c51491cc)

Implementing strong password practices

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/cc6baff2-4793-4b06-a583-fecffd05f465)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/0651b44d-b856-4731-8df2-3464c45b9de7)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/5631cbb9-67b4-48f9-9dbf-39a69114b4dd)

Changing file ownership and permissions

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/06604626-8089-4182-8c8b-e3b84c224a2b)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/58f2349b-6c59-49f3-8841-a69ee7186a37)

Adding a low privilege user
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/f0faf7de-3ef9-4200-b2f4-3ff6f9c36d22)

Adding the user to the sudoers list
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/767828f6-e8f2-4be6-8441-be97eac5f9ab)

![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/977eafc1-22ad-4e23-9431-b43995830e15)

adding to sudo visudo
Viewing the syslog
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/ef87926c-61d0-46e2-ad95-4d72a52f6016)

syslog
checking the previously logged in users
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/66750d6b-3659-436f-86cf-2c438c43f0ed)


auditctl
![image](https://github.com/kashmalahashmi/OsLabSpr23/assets/123877043/fecada24-7562-4a32-8bde-19ea70aaa9d3)

Task 02:
The lab's primary focus was on enhancing the security of a Linux system by implementing various best practices. Initially, we configured the firewall and proxy settings to block specific websites, such as Facebook, and redirected all traffic through Squid.

We ensured that the system was updated and all unnecessary services were disabled. Additionally, we used tools like ufw, nftables, and firewalld to create rules for network traffic.

To strengthen the system's security, we implemented strict password policies and learned how to create and manage users and their permissions using various Linux commands like chmod, chgrp, chown, and Access Control Lists (ACLs).

Moreover, monitoring the system is crucial to prevent any malicious activity, and we learned how to check syslog, currently and recently logged-in users using commands like last and w. Finally, we installed and configured auditd using the auditctl command to keep track of system activity.

Task 03, 04, 05 & 06
Lynis
Lynis is a security auditing tool for Unix and Linux-based systems that is available as open-source software. It runs various tests to evaluate the security status of the system, such as checking for misconfigured services, open ports, and vulnerable packages.

To utilize Lynis effectively, it is recommended to run it regularly with root privileges. It produces a substantial amount of output that can be challenging for some users to handle, and some of the suggested fixes may not be practical for specific systems. Other security auditing tools like OpenVAS and Nessus can be considered as alternatives.

OpenSCAP
OpenSCAP is a security compliance monitoring and scanning tool for Linux-based systems that is also available as open-source software. It offers a framework for enforcing security standards, such as those defined by the Center for Internet Security (CIS) benchmarks.

To make the most of OpenSCAP, you should first determine the security standards you need to comply with and configure the tool accordingly. The process can be automated to ensure continuous monitoring and compliance. OpenSCAP has a complex configuration process and may require customization to meet your specific needs. Other tools like CIS-CAT and Aqua Security's Kube-Bench can be considered as alternatives.

Nixarmor
Nixarmor is a Linux hardening tool that provides various security measures to protect against common attack vectors. Its features include process and network monitoring, file system protection, and kernel hardening.

To use Nixarmor effectively, you should first identify the security measures that are most important for your system and then configure the tool accordingly. This may involve creating custom rules or policies for specific processes or applications. Nixarmor is not as well-known or widely used as some of the other tools, making it harder to find support or troubleshooting help. Alternatives to Nixarmor include AppArmor and SELinux.
