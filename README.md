# control_dehumidificador
Circuit i software Esphom epr controlar el funcionament d'un deshumidificador

Problema:
En el soterrani d'una casa s'avumula molta humitat relativa que es filtra de les parets i del terra. Aixó causa problemes d'olors, floridures i insalubritat.
L'us d'un deshumidificador soluciona parcialment el problema evitant que la humitat relativa es mantigui alta amb el temps. El problema és que periodicament cal buidar el diposit d'aigua extreta del ambient i no sempre hi ha algú per fer-ho. 
Una possible solució seria conectar la sortida del diposit a un desaigua però al ser un soterrani el nivell de les canonades està per damunt del deshumidificador i cal utilitzar una bomba.

Proposta:
Crear un dispositiu Esphome (per integrar en ecosistema Home Assistant) que controli el funcionament del deshumidificador i accioni la bomba per buidar el diposit quan calgui. 

Material:
Placa ESP32 alimentada a 220V amb dos relés (1- per accionar el propi deshumidificador 2- per accionar la bomba), un sensor de temperatura/humitat, un sensor de nivell*.
(*Per evitar fallos montarem dos sensors: un basat en un iman i un sensor REED i un altre de digital sense contacte).

Material: 
ESP32: https://es.aliexpress.com/item/1005007481369265.html?spm=a2g0o.order_list.order_list_main.15.1ba0194dZFZamX&gatewayAdapt=glo2esp
https://github.com/xcusso/control_dehumidificador

