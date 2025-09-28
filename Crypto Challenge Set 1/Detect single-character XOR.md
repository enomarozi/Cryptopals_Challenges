<h1><b>Detect single-character XOR</h1></b>
<pre>
One of the 60-character strings in this <a href='https://cryptopals.com/static/challenge-data/4.txt'>file</a> has been encrypted by single-character XOR.
Find it.
</pre>
</b><h3>Solution</h3></b>

```console
root@Python:/home/venom/Downloads# wc -l 4.txt 
326 4.txt
```
<p>Terdapat 326 chipertext, kita diminta untuk mendapatkan plaintext dari semua kemungkinan kunci yaitu character 1 s/d 60. 
Yang nantinya kita akan mendapatkan 326 * 60 yaitu 19560 kemungkinan plaintext</p>

```python
import requests

def brute(cip, key):
    result = ''
    for i in bytes.fromhex(cip):
        text = i^key
        if text == 32 or (text >= 64 and text <= 122):
            result += chr(i^key)
    if len(result) >= 29:
        print(f"Result : {result}")
        print(f"Key : {chr(key)}")
    result = ''
            
with open('4.txt','r') as f: 
    for cip in f.readlines():
        for key in range(32,127):
            brute(cip.strip(),key)
```
<p>Output Program</p>
<pre>
Result : Now that the party is jumping
Key : chr(53)
Plaintext --> Now that the party is jumping
</pre>
</b><h3>Result</h3></b>
<pre>
Now that the party is jumping
</pre>
