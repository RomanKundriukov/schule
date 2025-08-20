Jede IP-Adresse teilt sich in Netz-Adresse und Host-Adresse. Die Subnetzmaske bestimmt, an welcher Stelle diese Trennung stattfindet. Die nachfolgende Tabelle enthält alle möglichen Subnetzmasken. Je nach verwendeter Netzwerk-Adresse und Subnetzmaske wird eine bestimmte Host-Anzahl in einem Subnetz adressierbar.

| Subnetzmaske      | Suffix  |
| ----------------- | ------- |
| **255.0.0.0**     | **/8**  |
| 255.128.0.0       | /9      |
| 255.192.0.0       | /10     |
| 255.224.0.0       | /11     |
| 255.240.0.0       | /12     |
| 255.248.0.0       | /13     |
| 255.252.0.0       | /14     |
| 255.254.0.0       | /15     |
| **255.255.0.0**   | **/16** |
| 255.255.128.0     | /17     |
| 255.255.192.0     | /18     |
| 255.255.224.0     | /19     |
| 255.255.240.0     | /20     |
| 255.255.248.0     | /21     |
| 255.255.252.0     | /22     |
| 255.255.254.0     | /23     |
| **255.255.255.0** | **/24** |
| 255.255.255.128   | /25     |
| 255.255.255.192   | /26     |
| 255.255.255.224   | /27     |
| 255.255.255.240   | /28     |
| 255.255.255.248   | /29     |
| 255.255.255.252   | /30     |

| Binär     | Dezimal |
| --------- | ------- |
| 1111 1111 | 255     |
| 1111 1110 | 254     |
| 1111 1100 | 252     |
| 1111 1000 | 248     |
| 1111 0000 | 240     |
| 1110 0000 | 224     |
| 1100 0000 | 192     |
| 1000 0000 | 128     |
| 0000 0000 | 0       |
