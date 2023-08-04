# Azure 2 vhub with spoke fw

This creates a vwan with 2 vwan hubs and a couple of spoke vnets with VM's connected to vhub1 and 2 and onprem vnets with a S2S tunnel to each hub. There is a firewall spoke connected to vhub1 with static routes directing all internet traffic from both hubs to that firewall. This creates a log analytics workspace and diagnostic settings for the firewall logs. You'll be prompted for the resource group name, your public ip and username and password to use for the VM's. NSG's are placed on the default subnets of each vnet allowing RDP access from your public ip. This also creates a logic app that will delete the resource group in 24hrs. The topology will look like this:

![image](https://github.com/quiveringbacon/Azure2vhubwithspokefw/assets/128983862/edf37300-b8a3-482b-aeb2-92894c2688d2)

You can run Terraform right from the Azure cloud shell by cloning this git repository with "git clone https://github.com/quiveringbacon/Azure2vhubwithspokefw.git ./terraform".

Then, "cd terraform" then, "terraform init" and finally "terraform apply -auto-approve" to deploy.
