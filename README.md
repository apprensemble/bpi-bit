# bpi-bit
mes debuts avec la bananapi bit

## recap

Depuis que j'ai le BPI-bit cad depuis que j'ai cree ce depot. J'ai testé les programme avec platformio, ça fonctionne.
J'ai testé blocky(webduino) mais ce n'est pas stable, l'ancienne version ne permet pas de bien exploité le potentiel de la carte et la nouvelle version plante au bout de qq minutes.
Des échanges sont en cours avec le développeur. Il dit ne pas être capable de reproduire le comportement de mes cartes :

[suivre la conversation](http://forum.banana-pi.org/t/how-to-bpi-bit-webduino-firmware-burning/5477)

Je vais devoir développer en C ou en Python. Je n'ai pas encore testé le firmware python, je prefere ne pas perdre plus de temps et faire du C.



## arduino ide

1) Dans les preferences ajouter https://git.oschina.net/dfrobot/FireBeetle-ESP32/raw/master/package_esp32_index.json
2) Puis dans le gestionnaire de carte installer firebeetle.

## blocky

1) aller sur https://blocklypro.webduino.io/dashboard
2) creer un nouveau fichier

## blocky pour bpi bit

1) aller sur https://bit.webduino.io/blockly/#8MAj7QPQ2b

Il est possible de simuler des scenario. mais Pour utiliser la plateforme il faut un autre firmware :

2) suivre cette doc : http://forum.banana-pi.org/t/how-to-bpi-bit-webduino-firmware-burning/5477
Ou depuis un gnux : 

```bash
esptool.py --port /dev/ttyUSB0 --baud 115200 write_flash --flash_mode dio --flash_size 4MB 0x1000 bootloader_dio_40m.bin 0x8000 partitions.bin 0xe000 boot_app0.bin 0x10000 bit_default.bin
```

3) rechercher sur le reseau wifi local bitXXXX / le mot de passe est 12345678
4) se connecter au 192.168.4.1 et ajouter votre point d'acces à la place de webduino.io
5) selectionner global dans le menu en bas si vous êtes hors de Chine puis valider.

6) vous pouvez vous y reconnecter depuis votre réseau local(seul vous pouvez connaitre l'ip)

7) copier le device id et l'entrer dans https://bit.webduino.io/blockly

   Tout ce que j'ai reussi à faire en mode block c'est programmer la matrice. C'est sympa mais il manque, les boutons, le buzzer, l'accelerometre etc...
   
   PS le firmware est là : https://github.com/yelvlab/BPI-BIT
