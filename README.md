# Лабораторная работа 1

**Название:** "Разработка драйверов символьных устройств"

**Цель работы:** "Получить знания и навыки разработки драйверов символьных устройств для операционной системы Linux."

## Описание функциональности драйвера

При записи в файл символьного устройства текста, содержащего цифры, должен запоминаться результат суммы всех чисел, разделенных другими символами (буквы, пробелы и т.п.). Последовательность полученных результатов с момента загрузки модуля ядра должна выводиться при чтении созданного файла в консоль пользователя.

## Инструкция по сборке

Сборка:

`make`

```
make -C /lib/modules/5.15.0-92-generic/build M="/home/vboxuser/input1.2" modules
make[1]: Entering directory '/usr/src/linux-headers-5.15.0-92-generic'
  CC [M]  /home/vboxuser/input1.2/ch_drv.o
  MODPOST /home/vboxuser/input1.2/Module.symvers
  CC [M]  /home/vboxuser/input1.2/ch_drv.mod.o
  LD [M]  /home/vboxuser/input1.2/ch_drv.ko
  BTF [M] /home/vboxuser/input1.2/ch_drv.ko
Skipping BTF generation for /home/vboxuser/input1.2/ch_drv.ko due to unavailability of vmlinux
make[1]: Leaving directory '/usr/src/linux-headers-5.15.0-92-generic'
```

## Инструкция пользователя

Передача строки в драйвер и чтение результата:

```bash
echo "123 456" > var3
cat var3
```

```
579
```

```bash
echo "123 456qwe23" > var3
cat var3
```

```
579
602
```

## Примеры использования

[Изображение](https://github.com/missmagenta/lab-1/blob/main/usage.jpg)

