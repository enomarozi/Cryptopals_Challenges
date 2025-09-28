<h1><b>Fixed XOR</h1></b>
<pre>
Hexa_1 = 1c0111001f010100061a024b53535009181c
Hexa_2 = 686974207468652062756c6c277320657965
</pre>
</b><h3>Solution</h3></b>
<p>Lakukan operasi XOR terhadap kedua nilai Hexadesimal, yang operasi XOR dilakukan per 1 bytes Hexadesimal yang secara berurut hingga 1 bytes Hexadesimal terakhir</p>

```python
val_1 = bytes.fromhex("1c0111001f010100061a024b53535009181c")
val_2 = bytes.fromhex("686974207468652062756c6c277320657965")
result = ''.join([hex(i^j).replace('0x','') for i,j in zip(val_1,val_2)])
print(f"Result Hexa : {result}")
print("Result Text :",bytes.fromhex(result))
```
<p>Output</p>
<pre>
Result Hexa :  746865206b696420646f6e277420706c6179
Result Text :  the kid don't play
</pre>
</b><h3>Result</h3></b>
<pre>
746865206b696420646f6e277420706c6179
</pre>
