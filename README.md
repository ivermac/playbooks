# Installation to make
- ansible
- vagrant and virtualbox

# Starting Vagrant
```
vagrant up
```

# Run the playbook
run `ansible-playbook web-notls.yml -vvvv`

# Generating TLS certificate
Create a `files` directory in the root if you don't have it already.
```
openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -subj /CN=localhost -keyout files/nginx.key -out files/nginx.csr
```

# Tips and tricks
```python
ansible all -a "date"
```

# Notes
Ansible looks for `host_vars` and `group_vars`. Ansible expects these directories to be either in the directory that contains your playbooks or in the directory adjacent to your inven‐ tory file. In our case, those two directories are the same.