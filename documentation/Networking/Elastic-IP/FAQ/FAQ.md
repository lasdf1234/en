# FAQ

**Q: Is the outbound of VM public network TCP 25 port limited?**

Precondition: It has been confirmed through inspection that both Security Group and firewall have no limit on the port.

Causes for limit: in order to improve the quality of emails sent from JD Cloud IP, the default is limiting Virtual Machine to sending emails and the email sending of destination port 25 being limited.



Method for lifting a ban: submit the Open Ticket to apply for the White List of Email Business requires the provision of the following:

1.IP that requires lifting a ban and associated domain names(three sets at most)

(1) Public IP and domain name (compulsory)

(2) Public IP and domain name (optional)

(3) Public IP and domain name (optional)

2. Type of the emails sent, for example: promotional emails (compulsory)

3. Number of emails sent per day, for example: 100,000/day (compulsory)

4. Is subscription is included? Yes/No (compulsory)

5. Description for use: it is more likely to be approved when the description is clear with less than 1,000 words (compulsory)

 

Note: if you file an application for lifting a ban, JD Cloud will deem it a default that you have confirmed and undertaken that if violations, such as SMTP sending junk mails, arise from the IP applied by you, JD Cloud will have the right to permanently ban TCP 25 port and no longer provider the service of lifting a ban. In case of any other doubts, please submit a ticket for consultation.

**Q: What is the peak-value of Elastic IP bandwidth？**

Currently, JD Cloud uses the industry-leading high-availability technology of the dual-active vRouter (Virtual Router). Compared with the traditional high-availability mode of the active and standby vRouter, the technology may provide link redundancy and high availability in scenarios such as high concurrent connections, large traffic load, and traffic bursts. With this technology, the maximum bandwidth of JD Cloud Elastic IP may reach 150% of the bandwidth actually purchased by a user, providing guarantee for the user’s business.

Based on the traffic sharing model of the dual-active vRouter, the maximum bandwidth of the Elastic IP is generally 150% of the bandwidth actually purchased by a user. In a rare special case, such as single access to FTP files, the maximum bandwidth of Elastic IP is around 75% of the bandwidth actually purchased by a user.

**Q: What is the inbound bandwidth of the Elastic IP? **

The rules for the allocation of Elastic IP inbound (from public network to JD Cloud) bandwidth of JD Cloud are described as follows:

1. If the IP outbound bandwidth purchased by a user is 100 Mbps or less, and the inbound bandwidth of 100 Mbps will be allocated to the IP.

2. If the IP outbound bandwidth purchased by a user is 100 Mbps or more, and the inbound bandwidth equal to the outbound bandwidth will be allocated to the IP.
