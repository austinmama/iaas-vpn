---

copyright:
  years: 1994, 2017-2019
lastupdated: "2019-03-06"

keywords: Linux Fedora, SSL VPN connections Windows, backend IP address

subcollection: iaas-vpn

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}

# Set up SSL VPN connections
{:#setup-ssl-vpn-connections}

Windows, Linux Fedora, and Linux require individualized connection instructions, which are shown in this document. Here are some examples of how you can use an SSL VPN connection:

* Remote Desktop to your server's backend IP address (10.4.X.X) for administration of your Windows 2003 servers.
* SSH to your server's backend IP address (10.4.X.X) for administering your UNIX servers.
* Use an IPMI client to control your server using the backend IPMI address (10.4.X.X). You can download the IPMI client tool once connected by going to http://downloads.softlayer.local/ipmi/ (You must be connected to SoftLayer Private VPN).
  * **Note:** IPMIView requires Java to be installed.  http://www.sun.com/java/
* Testing your website on the backend IPs before you make them live on your public IPs.
* File transfer of secure data between your server(s) and your home/office.
* Backup of configuration files your server(s) to your home/office.
* Securely connect to our [{{site.data.keyword.cloud}} Console](http://{DomainName}/).

## Windows (Internet Explorer)
{:#setup-ssl-vpn-connections-windows}

1. Open Internet Explorer and navigate to `https://www.ibm.com/cloud-computing/bluemix/vpn-access`.
* Once you have entered your username and password, you may be prompted to install an ActiveX plug-in. You must install this plug-in to connect to your backend network. 
* You also must have administrative rights on your workstation to install the ActiveX plug-in. If you do not have rights to install the plug-in, ask your local System Administrator to install it for you. 
* Once the ActiveX plug-in is installed, an Array SSL VPN network connector launches and establishes a connection to the VPN device. If successful, a red '**A**' appears in your task bar. You may click on the '**A**' at any time to see the status of your SSL VPN connection: its status, assigned IP address, assigned DNS servers, network routes, and time connected. 
* You may minimize your browser session at any time and continue to use other applications securely on the private network. 
* Once you are finished, disconnect by selecting the disconnect button to the right, or simply close the window.

## Linux Fedora 
{:#setup-ssl-vpn-connections-linux}

Firefox no longer supports NPAPI plugins (java applets). Use a different browser to perform these steps.
{:note}

It is recommended that you run all commands as root. (`setuid root`)

1. Download Java from `http://java.com/en/download/manual.jsp`. This is a Linux self-extracting file.
* Close your browser.
* Move the file to where you want to install Java (usually in `/usr/local`)
* Make the file executable using the command `chmod +x jre-6u1-linux-i586.bin`
* Run the installer using the command `./jre-6u1-linux-i586.bin`
* Agree to the terms and install.
* Once it is finished installed you must now create a symlink.

## Linux example
{:#setup-ssl-vpn-connections-linux-example}

1. Open your browser and go to `https://www.ibm.com/cloud-computing/bluemix/vpn-access`.
* Login with your console username and password.
* Once connected, select the **Network** tab.
* You should see a connect/install button. Select it and you should be prompted to install a Java component.
* Let the component install to the default path, which you might have to create manually. (`/usr/local/array_vpn`)
* After it is installed, a window should appear that says you are connected.
* This window must remain open to utilize the VPN tunnel, but you can minimize it.
* To test the connection, ping 10.0.80.11 or your server's private address. If you get a reply, you are successfully connected.
* When you are finished, select the disconnect button under the 'Network' tab, or simply close all of your browser windows.
