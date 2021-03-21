# Init new Vagrantfile
vagrant init vm-mysql

# Up VM with vagrant configuration
vagrant up vm-mysql

# Verify status vm
vagrant status vm-mysql

# Connection by SSH with username vagrant
vagrant ssh vm-mysql

# Turn off VM
vagrant halt vm-mysql

# Drop VM
vagrant destroy vm-mysql

# List boxes
vagrant box list

# Run provision shell specific
vagrant provision vm-mysql --provision-with shell-inline-name