

ansible-playbook -i inventory.yaml playbooks/ping.yaml

ansible-playbook -i inventory.yaml playbooks/shut_down.yaml --ask-become-pass