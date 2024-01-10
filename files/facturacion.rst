FACTURACIÓN ELECTRÓNICA
#######################

FA
========================

.. raw:: html

    <object data="../_static/assets/ventilator_pneumatics.pdf" type="application/pdf" width="700px" height="700px">
        <embed src="../_static/assets/ventilator_penumatics.pdf">
    </object><br>


   <p align ="justify"> El proceso inicia con una mezcla hde aire filtrado y oxigeno alimentada por un compressor pneumatico.
   El contenido de oxígeno es la mezcla es monitoreado por un medidor de oxigeno.
   El respirado monitorea el flujo de la mezcla de aire y oxigeno y se regula por medio de una valvula de control.
   La mezcla de aire oxigenado se envia al paciente.
   El aire que retorna del paciente pasa por un secador donde el aire seco se devuelve al ambiente y se drena la humedad </p> 
..


COMPONTENTES ELECTRÓNICOS
=========================

.. raw:: html

    <object data="../_static/assets/ventilator_schematic.pdf" type="application/pdf" width="700px" height="700px">
        <embed src="../_static/assets/ventilator_schematic.pdf">
    </object><br>

    <b>Esquema 1</b>

    <ol>
        <ul> Layout de conectores para usar con tarjeta Yubox  </ul>
        <ul> Circuito de filtrado para la senhal de comunicaciones I2C </ul>
        <ul>  Schematic del sensor (Falta el modelo del sensor?) de presion con conexiones de: poder (linea viva y tierra), referencia de senhal, puertos de comunicacion (I2C) </ul>
        <ul>  Schematic del sensor pe(Presión Barómetrica) presion diferencial (Sensirion SDP31-500PA): con conexions de: poder (línea viva y tierra) y puertos de comunicacion I2C  </ul>
    </ol>

    <b>Esquema 2</b>

    <ol>
        <ul>Convertidor de corriente de 120 voltios ac? a 5 voltios DC (voltaje del nodo Yubox?)</ul>
    </ol>

    <b>Esquema 3</b>

    <ol>
        <ul>Circuito para activar el buzzer (alarma) usando la salida de la tarjeta Yubox</ul>
    </ol>

    <b>Esquema 4</b>
    
    <ol>
     <ul> Circuido para medir la corriente que esta consumiendo el ventilador (compresor?), leer la cantidad de oxigeno, usando convertidores analogicos a digitales</ul>
    </ol>
..

.. include:: firmware.rst