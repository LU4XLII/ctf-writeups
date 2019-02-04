# Me= Ur_frnd - 150

I used uncompyle6 to decompile `share_plz.pyc`.

`uncompyle6 share_plz.pyz > share_plz.py`

```python
# uncompyle6 version 3.2.5
# Python bytecode 2.7 (62211)
# Decompiled from: Python 2.7.15+ (default, Aug 31 2018, 11:56:52)
# [GCC 8.2.0]
# Embedded file name: ctf.py
# Compiled at: 2018-12-17 05:54:10
import md5
md5s = [
 138940039282915521857245566551508789980L,
 301199927827248443324098746649658754844L,
 115532968768857561191818061218773701813L,
 191607221511277924288674550230099507123L,
 262751473846662512998464656050881387235L,
 75522546465545609216785689852028789081L,
 306267194955346451948103584154404505794L,
 81713620093652557693299093431127237017L,
 130346843513741821936326611370813041710L,
 267600260873798988999886324804713174180L,
 313232226741092686456213541074397062500L]
print 'Tell me something you know ...'
flag = raw_input("I'd prefer the flag: ")
if 'CTF' in flag:
    if len(flag) > 69:
        print "That's not the flag."
        exit()
    if len(flag) % 4 != 0:
        print "That's not the flag."
        exit()
    for i in range(0, len(flag), 4):
        s = flag[i:i + 4]
        if int('0x' + md5.new(s).hexdigest(), 16) != md5s[i / 4]:
            print "That's not the flag."
            exit()

    if md5.new(str(len(flag))).hexdigest() == 'f7177163c833dff4b38fc8d2872f1ec6':
        print 'Nice. Now submit the flag and get those points.'
    else:
        print "That's not the flag."
else:
    print 'Thanks for sharing. <3'
note = 'Comment this and any line(s), if exist, following this note.'
# okay decompiling share_plz.pyc
```

By analysing the code we notice that the hashes are calculated for every 4 chars. Then i wrote a script that bruteforced every 4 chars groups of the flag.

```python
import md5
import string
import itertools

md5s = [
 138940039282915521857245566551508789980L,
 301199927827248443324098746649658754844L,
 115532968768857561191818061218773701813L,
 191607221511277924288674550230099507123L,
 262751473846662512998464656050881387235L,
 75522546465545609216785689852028789081L,
 306267194955346451948103584154404505794L,
 81713620093652557693299093431127237017L,
 130346843513741821936326611370813041710L,
 267600260873798988999886324804713174180L,
 313232226741092686456213541074397062500L]
 
flag = 'BITSCTF{'
bruteforce_list = string.lowercase + string.digits + ' _}'
bruteforce_words = []

for i in itertools.product(bruteforce_list, repeat=4):
	bruteforce_words.append(''.join(i))

def compare(s, index):
    return int('0x' + md5.new(s).hexdigest(), 16) == md5s[index]

print flag
for i in range(2, 11):
    for j in bruteforce_words:
	if compare(j, i):
            flag += j
            print flag
            break
```

Result:

```
BITSCTF{
BITSCTF{unc0
BITSCTF{unc0mpyl
BITSCTF{unc0mpyl3_kn
BITSCTF{unc0mpyl3_kn0w5_
BITSCTF{unc0mpyl3_kn0w5_wh47
BITSCTF{unc0mpyl3_kn0w5_wh47_1_w
BITSCTF{unc0mpyl3_kn0w5_wh47_1_wr073
BITSCTF{unc0mpyl3_kn0w5_wh47_1_wr073_s0_
BITSCTF{unc0mpyl3_kn0w5_wh47_1_wr073_s0_s4d}
```

Flag: `BITSCTF{unc0mpyl3_kn0w5_wh47_1_wr073_s0_s4d}`
