# control_deshumidificador
Circuit i software Esphom epr controlar el funcionament d'un deshumidificador

Problema:
En el soterrani d'una casa s'acumula molta humitat relativa que es filtra de les parets i del terra. Aixó causa problemes d'olors, floridures i insalubritat.
L'us d'un deshumidificador soluciona parcialment el problema evitant que la humitat relativa es mantigui alta amb el temps. El problema és que periodicament cal buidar el diposit d'aigua extreta del ambient i no sempre hi ha algú per fer-ho. 
Una possible solució seria conectar la sortida del diposit a un desaigua però al ser un soterrani el nivell de les canonades està per damunt del deshumidificador i cal utilitzar una bomba.

Proposta:
Crear un dispositiu Esphome (per integrar en ecosistema Home Assistant) que controli el funcionament del deshumidificador i accioni la bomba per buidar el diposit quan calgui. 

Material:
Placa ESP32 alimentada a 220V amb dos relés (1- per accionar el propi deshumidificador 2- per accionar la bomba), un sensor de temperatura/humitat, un sensor de nivell*.
(*Per evitar fallos montarem dos sensors: un basat en un iman i un sensor REED  que funcionarà a 220V i un altre de digital sense contacte).

ESP32: https://es.aliexpress.com/item/1005007481369265.html?spm=a2g0o.order_list.order_list_main.15.1ba0194dZFZamX&gatewayAdapt=glo2esp
Sensor nivell REED: https://es.aliexpress.com/item/1005005648584783.html?spm=a2g0o.order_list.order_list_main.32.1ba0194dZFZamX&gatewayAdapt=glo2esp
Sensor de nivell digital: https://es.aliexpress.com/item/1005004159360740.html?spm=a2g0o.order_list.order_list_main.38.1ba0194dZFZamX&gatewayAdapt=glo2esp
El sensor comprat es NPN (existeixen versions PNP i RS485
Sensor temp/humitat: https://es.aliexpress.com/item/1005005337815331.html?spm=a2g0o.order_list.order_list_main.21.1ba0194dZFZamX&gatewayAdapt=glo2esp
Bomba (opcional): https://es.aliexpress.com/item/1005002357671420.html?spm=a2g0o.order_list.order_list_main.44.1ba0194dZFZamX&gatewayAdapt=glo2esp

Connexionat:
Conectarem alimentació 5V i massa al sensor digital i la sortida al GPIO 13 en mode PULLUP. 
Connectarem el sensor temp i humitat a VCC i masa, SDA GPIO 21 i SCL GPIO 22
El sensor REED el posarem an paralel amb el relé 220V d'alimentació de la bomba. D'aquesta manera, si per algun motiu es queda penjat el ESP32 quan arribi al nivell del sensor s'activarà la bomba.
Els reles estan conectats als GPIO16 i GPIO17
Conectarem el RELE 1 per alimentar el deshumidificador i el RELE 2 per alimentar la bomba.



