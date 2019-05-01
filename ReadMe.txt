setup Kubernetes on RedHat Linux

- > Pre-Steps:
  Make sure all the machines you gonna use kubernetes should disable SElinux and swap and Enable br_netfilter.
  
  Disable SELinux : 
        # setenforce 0
        # sed -i --follow-symlinks 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux

  Disable Swap
        # swapoff –a
  
  Enable Br-netfilter
        # modprobe br_netfilter
        # echo '1' > /proc/sys/net/bridge/bridge-nf-call-iptables

- > Installing dependencies
    Before start to kubernetes, we must install the docker tools, to install use following commands,

    # yum install -y yum-utils device-mapper-persistent-data lvm2
    Now, add the Docker-ce repository with the command:
    # yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
    
