```
ansible-playbook -i hosts provision.yml --user=vagrant --ask-pass
ansible-playbook -i hosts provision.yml --user=cristopher --ask-pass --ask-become-pass