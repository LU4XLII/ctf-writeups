# keyboard - 60 points

After extracting the file `submit_the_flag_that_is_here.txt` we found some hashes. A quick test with [crackstation](http://crackstation.net/) gave us a start point.

![hash](./hash.png)

```python
import string
import hashlib
import re

with open('submit_the_flag_that_is_here.txt', 'r') as f:
    text = f.read()

for i in string.printable:
    chr_md5 = hashlib.md5(i.encode('utf-8')).hexdigest()
    chr_sha256 = hashlib.sha256(i.encode('utf-8')).hexdigest()
    text = text.replace(chr_md5, i).replace(chr_sha256, i)

regex = re.compile('(F # {[\w ]+})')
print(regex.findall(text)[0].replace(' ', ''))
```

Flag: `F#{Y3aH_Y0u_kN0w_mD5_4Nd_Sh4256}`
