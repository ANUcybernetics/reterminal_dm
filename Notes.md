# reTerminal

## cmdline.txt  

logo.nologo vt.global_cursor_default=0 console=tty0 loglevel=0

## config.txt   

i2c_arm=on
enable_uart=1
dtoverlay=dwc2,dr_mode=host
dtparam=ant2
disable_splash=1
ignore_lcd=1
dtoverlay=vc4-kms-v3d-pi4
dtoverlay=i2c3,pins_4_5
gpio=13=pu
dtoverlay=reTerminal,tp_rotate=1


## Modules

mipi_dsi
ltr30x
lis3lv02d
bq24179_charger


------------------------


# reTerminal DM

## cmdline.txt

logo.nologo 
vt.global_cursor_default=0
console=tty3
loglevel=0

## config.txt   

dtparam=i2c_arm=on
dtparam=i2c_vc=on
dtparam=i2s=on
dtparam=spi=on

enable_uart=1
dtparam=ant2
disable_splash=1
ignore_lcd=1


dtoverlay=dwc2,dr_mode=host
dtoverlay=vc4-kms-v3d-pi4
dtoverlay=i2c1,pins_2_3
dtoverlay=i2c3,pins_4_5
dtoverlay=imx219,cam0

dtoverlay=reTerminal-plus

// comment old values
gpio=13=pu
dtoverlay=reTerminal,tp_rotate=1
dtoverlay=reTerminal-bridge


## Modules

* ltr30x
* ili9881d
* ch34x
* rtc-pcf8563w

Disable 

* cdc_acm



------------------------

# reComputer r100x

## Hardware

* i2c
* rtc
* buzzer
* accelerometer
* light sensor
* backlight 

## cmdline.txt

## config.txt   

dtparam=i2c_arm=on
dtparam=spi=on
enable_uart=1

dtoverlay=dwc2,dr_mode=host
dtoverlay=vc4-kms-v3d
dtoverlay=audremap,pins_18_19
dtoverlay=i2c1,pins_44_45
dtoverlay=i2c3,pins_2_3
dtoverlay=i2c6,pins_22_23

dtoverlay=reComputer-R100x,uart2

## Modules

rtc-pcf8563w

## TODO

rs485_control_DE -> requires libgpiod-dev
gcc tools/rs485_control_DE/rs485_DE.c -o tools/rs485_control_DE/rs485_DE -lgpiod || exit 1;
cp tools/rs485_control_DE/rs485_DE /usr/local/bin || exit 1;

