# Current OpenConfig Tree

See current-tree.txt

### Regenerate tree

```bash
python3 -m venv env
. env/bin/activate
pip install -r requirements.txt
pyang -f tree $(find public/release/models/ -type f -name '*.yang' | sed -r 's|/[^/]+$||' | sort | uniq | while read line; do echo -ne "$line/*.yang " ; done) > current-tree.txt
```
