<h1><b>Convert hex to base64</h1></b>
<pre>
The string:

49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d
</pre>
</b><h3>Solution</h3></b>
<p>Convert hexa to ascii dan encode ke base64</p>

```python
from base64 import b64encode

text = bytes.fromhex('49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d')
result = b64encode(text).decode('ascii')
print("Result Base64 :",result)
print("Result Decode :",text)
```
<p>Output</p>
<pre>
  Result Base64 : SSdtIGtpbGxpbmcgeW91ciBicmFpbiBsaWtlIGEgcG9pc29ub3VzIG11c2hyb29t
  Result Decode : I'm killing your brain like a poisonous mushroom
</pre>
</b><h3>Result</h3></b>
<pre>
SSdtIGtpbGxpbmcgeW91ciBicmFpbiBsaWtlIGEgcG9pc29ub3VzIG11c2hyb29t
</pre>
