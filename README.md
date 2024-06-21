# Event Driven Ansible

## Prepare

```bash
pip3 install -r requirements.txt
ansible-galaxy install -r requirements.yml
. venv/bin/activate
```

## Running

Start

```bash
ansible-rulebook --rulebook rulebooks/webhook.yml -i inventory --print-events --verbose
```


### Collect information

```bash
curl -X POST http://localhost:5000 \
  -H "Content-Type: application/json" \
  -d '{"action":"collect_information","hosts":"localhost,other-host.example.com"}'
```

### Force fsck


```bash
curl -X POST http://localhost:5000 \
  -H "Content-Type: application/json" \
  -d '{"action":"fsck","hosts":"localhost,other-host.example.com"}'
```
