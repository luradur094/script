## Codigo del script 
Aqui os dejo el codigo del script para que lo proveis o modifiqueis
a vuestro gusto o utilidad, espero que os sirva de ayuda 

#!/bin/bash
#parametro
#variables
red="192.168.2"
#funciones
encabezado (){
clear
echo "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@"
echo "ordenadores conectados"
echo "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@"
}
conec (){
    for i in $(seq 1 1 10)
    do
    respuesta=$(ping -w 1 $red.$i |grep -w "received"|cut -d" " -f4)
    if [ $respuesta -eq 1 ]
    then
    echo "$red.$i esta conectado"
    fi

    done
}
#bloque principal
encabezado
conec