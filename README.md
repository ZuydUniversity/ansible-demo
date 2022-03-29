Create python venv
```
python -m venv .venv
source .venv/bin/activate
```


Install ansible[azure]
```
pip install 'ansible[azure]'
```

Install azure
```
pip install -r requirements-azure.txt
```






Create ssh key in folder .azure/ssh_keys folder

```
mkdir .azure/ssh_keys
cd .azure/ssh_keys
ssh-keygen -m PEM -t rsa -b 4096
location: .azure/ssh_keys/id_rsa
```


Create credentials file in .azure folder

```
cd ..
touch credentials
```

Add the following details

```
[default]
client_id=xxxxxxxxx
object_id=xxxxxxxxx
tenant=xxxxxxxxx
secret=xxxxxxxxx
subscription_id=xxxxxxxxx
```


```
ansible-playbook main.yml
ansible-inventory -i myazure_rm.yml --graph
ansible-inventory -i myazure_rm.yml --list
ansible-playbook ping.yml -i myazure_rm.yml
```