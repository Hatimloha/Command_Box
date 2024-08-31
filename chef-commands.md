# Chef Commands

## 1. Runs the Chef client, which applies the configuration to the node.
```bash
chef-client
```
- Single recipe execute:
```bash
chef-client –zr "recipe[apache-cookbook::recipe3]"
```

- Multiple recipes execute:
```bash
chef-client –zr "recipe[test-cookbook::default], recipe[apache-cookbook::default]"
```

## 2. The Swiss Army knife of Chef, used for managing nodes, cookbooks, roles, environments, and more.
```bash
knife
```
- Upload a cookbook:
```bash
knife cookbook upload apache-cookbook
```

- Check uploaded files on server:
```bash
knife cookbook list
```
- Run list according to server (only recipes we want to run on a particular server will run):
```bash
knife node run-list set node1 "recipe[apache-cookbook::apache-recipe]"
```
- Delete a cookbook:
```bash
knife cookbook delete <cookbook name> -y
```
- To check the number of client nodes connected to the server:
```bash
knife node list
```
- Clients present on nodes that are connected to the server:
```bash
knife client list
```
- To delete a connected client from the server:
```bash
knife role delete <role-name> -y
```
- To delete a Chef role:
```bash
knife role delete <role-name> -y
```
- Upload the role on Chef server:
```bash
knife role from file /devops.rb
```
- To check roles stored in Chef server:
```bash
knife role list
```

## 3. Runs Chef in a standalone mode without a Chef server, useful for testing or simple deployments.
```bash
chef-solo
```
- Example usage:
```bash
sudo chef-solo -c solo.rb -j solo.json
```  
## 4. Interactive shell for exploring the Chef server API and testing recipes.
```bash
chef-shell
```































#Chef-Commands
#1 Runs the Chef client, which applies the configuration to the node.
chef-client
  #single recipe exicute
  chef-client –zr "recipe[apache-cookbook::recipe3]"
  #multiple recipe exicute
  chef-client –zr "recipe[test-cookbook::default], recipe[apache-cookbook::default]" 

#2 The Swiss Army knife of Chef, used for managing nodes, cookbooks, roles, environments, and more
knife
  #Upload a cookbook
  knife cookbook upload apache-cookbook 
  #Check upload file on sever
  knife cookbook list 
  #Run list according to sever (only recipe we want to run on particular server will run) 
  knife node run-list set node1 "recipe[apache-cookbook::apache-recipe]"
  #Use to delete cookbook
  Knife cookbook delete <cookbook name> -y
  #To check number Of client node connected to server 
  Knife node list 
  #client present on node which are connected to server 
  Knife client-list
  #To delete connected client to server
  Knife client delete <client-name> -y 
  #To delete chef role
  Knife role delete <role-name>  -y 
  #Now upload the role on chef-server 
  knife role from file/devops.rb 
  #To check role store in chef server 
  knife role list 
  

#3 Runs Chef in a standalone mode without a Chef server, useful for testing or simple deployments.
#The chef-solo command is used to run Chef in a standalone mode without a Chef server. It is typically used for simple deployments, testing, or when you don't have a Chef server available.
chef-solo
  sudo chef-solo -c solo.rb -j solo.json

#4 Interactive shell for exploring the Chef server API and testing recipes.
chef-shell

#5 Applies a single recipe from the command line without a Chef server.
chef-apply
  #only use when we dont have chef server
  chef-apply my_recipe.rb

#6 Manages encrypted data bags using keys from a key/value store.
chef-vault
  #Create a voult and add file
  chef-vault create my_vault my_item --json '{"username": "admin", "password": "s3cr3t"}'
  #To add existing file in vault 
  chef-vault update my_vault my_item --json '{"username": "new_admin", "password": "new_s3cr3t"}'
  #To check file inside a vault
  chef-vault show my_vault my_item
  #To delete a file from vault
  chef-vault delete my_vault my_item

#7 Controls the Chef server, including starting, stopping, reconfiguring, and managing services.
chef-server-ctl

#8 Bootstraps a new node to be managed by Chef.
knife bootstrap
  #bootstrap is use to connect node with server 
  Knife bootstrap <private-ip> -- ssh-user ec2-user  --sudo -I node-key pem –n node 1

#9 This cmd is used to ignore recipe which we don’t want to commit same as "gitignore"
chefignore

#10 Testing cookbook is proper or not without deploying on live server "demo run".
Kitchen.yml

#11 Information like name, version, author etc of cookbook
Metadata rb 

#12 Use this for opening existing file for changes 
.Rb

#13 Information about usage of cookbook 
Readme md

#14 Here we write code 
Recipe
  #Command for create a recipe
  Chef generate recipe <recipe name>

#15 Create cookbook for store recipe
cookbook
  #Command for create a cookbook
  Chef generate cookbook <cookbook name>

#16 unit testing 
Spec 
  #If you want to test a small part of script(unit)  
  Chef spec ruby –c  test-cookbook/recipe/test-recipe.rb 

#17 integration testing (entire) 
Test
  chef exec ruby -c test-cookbook/recipe/recipe2.rb

 
