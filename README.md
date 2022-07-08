1. Create Directory 

    mkdir -p quiz2/group_vars
    cd quiz2/group_vars

2. Create Managed File list

    managed1-host-diofathurr
    managed2-host-diofathurr

3. create file ansible.cfg

    vi ansible.cfg

        [defaults]
        inventory = ./inventory

4. create inventory

    vi inventory

        [group name]
        <server name>

        [group name]
        <server name>
    
5. create secret

    vi secret.yml

        pass=<password>

6. run vault encrypt

    ansible-vault encrypt secret.yml
    password=<password>
    re-enter password =<password>

7. create file playbook

    vi <name_file>.yml

8. run playbook 

    ansible-playbook --syntax-check --ask-vault-pass <name_file>.yml
    echo 'password' > vault-pass
    chmod 600 vault-pass
    ansible-playbook --vault-password-file=vault-pass <nama_file>.yml

9. verify user

    ssh <nama_server> 
    run /etc/passwd