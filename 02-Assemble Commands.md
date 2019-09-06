---


---

<h3 id="leave">leave</h3>
<p>메모리 초기화 후 메모리 베이스를 ebp에 맞춘다.</p>
<pre><code>mov esp, ebp
pop ebp
</code></pre>
<h3 id="ret">ret</h3>
<p>다음 장소로 이동한다.</p>
<pre><code>pop eip
jmp eip
</code></pre>

