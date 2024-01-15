Retenciones
###########


Retención de cliente
~~~~~~~~~~~~~~~~~~~~

El :guilabel:`Retención cliente` es un documento no electrónico para su empresa, este documento es
emitido por el cliente para aplicar una retención a la venta.

Es necesario disponer de una factura validada (contabilizada) para poder registrar una retención de cliente. En
la factura hay un botón llamado :guilabel:`Add Withhold`, haga clic en este botón para ser dirigido
haga clic en este botón para acceder al formulario :guilabel:`Retención de cliente` y, a continuación, complete la siguiente información:

- :guilabel:`Número de documento`: escriba el número de retención.
- :guilabel:`Líneas de Retención`: seleccione los impuestos que retiene el cliente.

Antes de validar la retención, revise que los importes de cada impuesto coincidan con los del documento original.
documento.

.. image:: ecuador/retencion-cliente.png
   :align: center
   :alt: Retención al cliente para Ecuador.



Retención de proveedor
~~~~~~~~~~~~~~~~~~~~~~

La :guilabel:`Retención de compras` es un documento electrónico que, una vez validado, se envía al SRI.

Es necesario disponer de una factura en estado validado para poder registrar una :guilabel:`Purchase
de compras`. En la factura, hay un botón llamado :guilabel:`Añadir Retención`, haga clic en este botón
para acceder al formulario :guilabel:`Withholding` y rellene los siguientes datos:

- :guilabel:`Número de documento`: escriba el número de documento (secuencia), sólo tendrá que hacerlo
  sólo tendrá que hacerlo una vez, la secuencia se asignará automáticamente para los siguientes documentos.
- :guilabel:`Líneas de retención`: Los impuestos aparecen automáticamente según la configuración de
  productos y proveedores, debe revisar si los impuestos y el soporte fiscal son correctos, y, si no es
  no es correcto, puede editar y seleccionar los impuestos y soporte fiscal correctos.

Una vez revisada la información puede validar la :guilabel:`Retención`.

.. image:: ecuador/compra-retencion.png
   :align: center
   :alt: Retención de compras para Ecuador.

.. nota::
   No se puede cambiar el soporte de impuestos por uno que no se haya incluido en la configuración de los impuestos
   utilizados en la :guilabel:`Factura Proveedor`. Para ello, vaya al impuesto aplicado en la :guilabel:`Factura de proveedor
   y cambie allí el :guilabel:`Soporte fiscal`.

Una retención puede dividirse en dos o más líneas, esto dependerá de si se aplican dos o más
porcentajes de retención.

.. example::
   El sistema le propone una retención de IVA del 30% con soporte fiscal 01, usted puede añadir su retención de IVA del
   retención del 70% en una nueva línea con el mismo soporte fiscal, el sistema se lo permitirá siempre y cuando
   el total de las bases coincida con el total de la :guilabel:`Factura Proveedor`.
