# SMT32MP15x

## STM32MP157D-DK1
[STM32MP157D-DK1](https://www.st.com/ja/evaluation-tools/stm32mp157d-dk1.html)を購入

## 参考サイト

https://wiki.st.com/stm32mpu/wiki/Category:STM32MP15_Discovery_kits

https://zenn.dev/waarrk/articles/aae4a6caadf9d3


## Hello World

1. 付属のMicroSDを挿す
    - おそらく[Starter package](https://wiki.st.com/stm32mpu/wiki/STM32MP15_Discovery_kits_-_Starter_Package)が入っている
2. STLinkのMicroUSBを挿す
    - USB-シリアルとしてデバッグCLIが使える
    - 115200bps
    - 多分イーサネットつないだり、HDMI接続&USBキーボードなどでも操作可能
3. PWRのUSB-TypeCを接続する(5V-3Aらしい)
4. 起動後、操作を受け付けるようになったら以下でCM4を実行できる
```
cd /usr/local/Cube-M4-examples/STM32C-DK2/Examples/GPIO/GPIO_EXTI
./fw_cortex_m4.sh start
```
5. USER1ボタンを押すとLD7がトグルする