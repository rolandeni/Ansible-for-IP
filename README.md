## Break down of ip_utils.yaml script
1. The hosts line specifies which hosts the script should run on.
2. become: yes tells Ansible to run the script with elevated privileges (i.e., as the root user).
3. The vars section defines variables for the interface name, IP address, and subnet mask.
4. The tasks section contains the actual steps to be executed on the host(s).
5. The first task is named "Install ip utility" and installs the iproute2 package (which includes the ip utility) using the apt package manager.
6. The second task is named "Add logical IP address" and uses the shell module to execute the ip addr add command with the specified IP address, subnet mask, and interface name.
7. Assuming that the variables are correctly defined and the iproute2 package is not already installed, this script should successfully install ip utils and add the specified logical IP address to the specified interface.

## Break down of ip_module.yaml 

In this script, the **vars** section defines the interface name, IP address, and subnet mask as variables. The tasks section contains a single task named *"Add new IP address"* that uses the shell module to execute the ip address add command with the specified IP address, subnet mask, and interface name.

When you run this Ansible script on a host, it will provision the new IP address on the specified interface. Note that this script assumes that the server already has the necessary network infrastructure in place to support the new IP address. You may need to configure DNS, routing, and firewall rules as appropriate to ensure that the new IP address is accessible from other hosts.
