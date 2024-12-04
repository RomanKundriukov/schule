## Commands

<table>
<thread>
<tr>
<th>Behefl</th>
<th>Beschreibung</th>
</tr>
</thread>
<tr>
<td>ipconfig /all</td>
<td>Zeigt alle Netzwerkadapter-Infos wie MAC-Adresse und DHCP-Status.</td>
</tr>
<tr>
<td>ping ipv4</td>
<td>Testet Konnektivität, Erreichbarkeit und Latenz zu einem Server.</td>
</tr>
<tr>
<td>
<p>1. switch> enable</p>
<p>2. switch# configure terminal</p>
<p>3. switch(config)# interface fa0/1</p>
<p>4. switch(config-if)# mdix auto</p>
<p>5. switch(config-if)# end</p>
</td>
<td>
Aktivierung von Auto-MDIX:
</td>
</tr>
<tr>
<td>ip route 10.1.1.0 255.255.255.0 209.165.200.226</td>
<td>Das Kommando fügt eine statische Route in die Routing-Tabelle ein. Es bedeutet:
 Pakete für das Zielnetzwerk 10.1.1.0/24 (Subnetzmaske: 255.255.255.0) sollen über den nächsten Hop (Router) mit der IP-Adresse 209.165.200.226 geleitet werden.
</td>
</tr>
<tr>
<td>tracet "Ziel IP-Adresse oder Host-Name"</td>#
<td>IPv4: Der Befehl sendet ICMP (oder manchmal UDP)-Pakete mit einer inkrementellen TTL (Time-To-Live). Jeder Router, der das Paket weiterleitet, reduziert die TTL um 1 und sendet bei Erreichen von TTL = 0 eine ICMP-Fehlermeldung zurück.
Zweck: Es hilft, Netzwerkprobleme zu diagnostizieren, z. B. Verzögerungen oder Ausfälle auf bestimmten Routen.</td>
</tr>
</table>