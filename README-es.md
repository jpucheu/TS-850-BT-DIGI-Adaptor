[Español](README-es.md) | [English](README.md)

# Interfaz de modos digitales inalámbrica para transceptores de la serie Kenwood TS-850
**NOTE: Diseño en estado experimental!! Todo puede cambiar**

## Índice
- [Actualizaciones](#update-es)
- [Atención!](#important-es)
- [Contexto](#background-es)
- [Diseño](#design-es)
- [Repositorios del código](#code-repositories)
- [Configuración del JDY-67](#configuration-of-JDY-67)
- [FT8 para Android](#related-efforts)
- [Colaboradores](#contributing)
- [Maintainers](#maintainers)
- [Licencia](#license)

## Actualizaciones

### 01092023 - Diseño inicial
1. Actualización de la documentación al idioma español y características del TS-850

## Atención!
1. Verificar que la versión del firmware en el módulo JDY-67 sea 1.3 o superior. 
2. Este módulo NO posee control de flujo por hardware, lo cual complica el diseño para transceptores que no poseen PTT por CAT. 

## Background
My friend BG6JJI designed a Bluetooth DIGI adaptor working for many old style TRXs with a Bluetooth, DIGI and CAT ability. He was using a Bluetooth module named JDY-67. I am not sure which manufacturer made the JDY-67. But it's really inexpensive and really works for Bluetooth Audio, and SPP in same time.

So, I pick up an old PCB design for my FT-818. It was design for FT8 cable connecting at very beginning. However, with JDY-67, It should works for Bluetooh/DIGI/CAT. I'd measured the DATA and ACC jacks on FT-818's rear panel, And refering to the FT-817ND's Service Manual, I think the Yaesu's PCB maybe design in a 0.635mm/0.025inch grid. Under this assumption, I'd drawn a PCB that could cover most of the FT-817 rear panel, and perfectly matched all the screw holes, jacks....precisely!!! It looks like a underwear(under-bottom-hardware), right?

![have a look](./pics/FT-81x-BT-DIGI-Adaptor-PIC.png)

Although FT-817/818 has been discontinued, I still love this twenty years selling product. Now, I would like to share this PCB desgin to all HAM communities, If you wanna make your design, you can make any modify from it.


## Design
This PCB was design by KiCad 7.0
In the Layer User.Drawings and User.Comments, there are some information of measurement.
In the Layer User.1~4, there are approximate FT-817/818's panel sketch for comparison.

![have a look](./pics/FT-81x-BT-DIGI-Adaptor-SCH.png)
![have a look](./pics/FT-81x-BT-DIGI-Adaptor-PCB.png)
![have a look](./pics/FT-81x-BT-DIGI-Adaptor-3D.png)


## Code Repositories

- Github [https://github.com/BG6LH/FT-81x-BT-DIGI-Adaptor](https://github.com/BG6LH/FT-81x-BT-DIGI-Adaptor)
- Gitee [https://gitee.com/bg6lh/FT-81x-BT-DIGI-Adaptor](https://gitee.com/bg6lh/FT-81x-BT-DIGI-Adaptor)


## Configuration of JDY-67

Please note, the JDY-67's default BAUD is 9600bps.

Before connect the adaptor to phone or computer, there are three bluetooth configuration need to be changed. please use those serial port AT instructions:
```sh
AT+SING1\r\n
# Turn on single-ended output 

AT+ROLE0\r\n
# Turn off BLE bluetooth

AT+CALEN1\r\n
# Turn on the phone function

AT+RST\r\n
# Restart the moudule
```
Jdy-67 module serial command must be plus \r\n .

## Related Efforts
- [FT8CN for Android](https://github.com/N0BOY/FT8CN) - Run FT8 natively on Android. This app works well with our Bluetooth DIGI Adaptor.


## Contributing
With special thanks to **BG6JJI, BI1EIH***. They give me many generous advice.

Let's enjoy the FT-817's last lucky underware together!!

## Maintainers
- [@BG6LH(me)](https://github.com/BG6LH)
- [@sgub(BI1EIH)](https://github.com/sgub)

## License

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)][cc-by-nc-sa].

[![CC BY NC SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: https://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png
