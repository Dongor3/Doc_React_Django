
Introducción
============

Con la localización ecuatoriana puede generar documentos electrónicos con su XML, folio Fiscal,
con firma electrónica y conexión directa al SRI.

Los documentos soportados son Facturas, Notas de Crédito, Notas de Débito, Liquidaciones de Compra y
Retenciones de Venta/Compra, Guías de Remisión.

La organización territorial ecuatoriana está incluida en la localización, lo que permite agregar a los Contactos
Provincias, Cantones y Parroquias.

.. note::
   La localización ecuatoriana está disponible en el siguiente repositorio


Instalación de los Módulos
--------------------------

:ref:`Install <general/install>` Los módulos pertenicien
localization:

.. list-table::
   :header-rows: 1
   :widths: 25 25 150

   * - Name
     - Technical name
     - Description
   * - :guilabel:`Localizacón Base`
     - `l10n_ec_base`
     - El paquete por defecto :doc:`fiscal localization package <../fiscal_localizations>`, agrega características contables
       características para la localización ecuatoriana, las cuales representan la configuración mínima
       requerida para que una empresa opere en Ecuador de acuerdo a los lineamientos establecidos por la
       :abbr:`SRI (servicio de rentas internas)`. The module's installation automatically loads:
       Plan contable, impuestos, tipos de documentos, tipos de soporte fiscal. Además, la generación de
       formularios 103 y 104 es automática.
   * - :guilabel:`Documentos Electrónicos`
     - `l10n_ec_edi`
     - Incluye todos los requisitos técnicos y funcionales para generar y validar
       :doc:`Documentos Electrónicos
       <../contabilidad/facturas_clientes/factura_electronica>`, basado en la Documentación Técnica
       publicada por el SRI. Los documentos autorizados son: Facturas, Notas de Crédito,Liquidaciones de Compra 
  


.. note::
   When you install a database from scratch selecting `Ecuador` as the country, Odoo automatically
   installs the base module :guilabel:`Ecuadorian - Accounting`.

Configurar Compañia
-------------------

Para configurar la información de su empresa, vaya a la aplicación :guilabel:`Contacts` y busque el nombre dado
a su empresa o active :ref:`modo-desarrollador <modo-desarrollador>` y vaya a :menuselection:`Empresa
--> Contacto` y luego edita el contacto para configurar la siguiente información:

#. Marque la opción :guilabel:`Empresa` en la parte superior

   - :guilabel:`Nombre
   - :guilabel:`Dirección`
   - :guilabel:`Número de identificación`
   - :guilabel:`Tipo de contribuyente
   - :guilabel:`Teléfono`
   - :guilabel:`Email`

#. Suba el logotipo de la empresa y s

.. image:: img/companie.png
   :align: center
   :alt: Populate company data for Ecuador in Odoo Contacts.

Documentos Electrónicos
-----------------------

Para cargar su información para documentos electrónicos vaya a :menuselection:`Contabilidad -->
Configuración --> Ajustes` y busque :comando:`Localización Ecuatoriana`.


Configure la siguiente información:


- :guilabel:`Nombre legal de la empresa`.
- :guilabel:`Utilizar servidores de producción`: marque la casilla si su empresa va a realizar documentos electrónicos en un entorno de producción.
  documentos en el entorno de producción. Si desea utilizar el entorno de pruebas para los documentos
  entonces mantenga la casilla desmarcada.
- :guilabel:`Régimen`: seleccione si su empresa está en Régimen General Ordinario o está calificada como RIMPE.
- :guilabel:`Obligado a llevar libros contables`: marque la casilla si su empresa tiene esta
  condición.
- :guilabel:`Impuestos por defecto para las retenciones`.
- :guilabel:`Emitir retenciones`: marque la casilla si su empresa va a realizar retenciones electrónicas.
  electrónicas.
- :guilabel:`Retener consumibles`: ponga el código de la retención para cuando compre bienes.
- :guilabel:`Retener servicios`: ponga el código de la retención para cuando compre servicios.
- :guilabel:`Retener tarjeta de crédito`: ponga el código de la retención para cuando compre con tarjeta de crédito
  tarjeta de crédito
- :guilabel:`Número de agente de retención`: ponga el número de resolución del agente de retención de la empresa, si
  aplicable a su empresa.
- :guilabel:`Archivo de certificado electrónico`: cargue el certificado electrónico y la contraseña, y guárdelo.
- :guilabel:`Número de contribuyente especial`: si su empresa está calificada como contribuyente especial,
  rellene este campo con su correspondiente número de contribuyente.

.. image:: ecuador/firma-electronica.png
   :align: center
   :alt: Firma electrónica para Ecuador.



VAT withholding
---------------

This configuration only applies if you are qualified as a *Withholding Agent* by the SRI, otherwise
skip this step. To configure your VAT withholding, go to :menuselection:`Accounting --> Accounting
--> Configuration --> Ecuadorian SRI: Taxpayer Type SRI`.

You must configure the withholding percentage that applies for each type of taxpayer, specify the
:guilabel:`Goods VAT Withholding` and the :guilabel:`Services VAT Withholding`.

.. image:: ecuador/contributor-type.png
   :align: center
   :alt: Taxpayer Type configuration for Ecuador.

.. tip::
   In the case that the :guilabel:`Taxpayer Type` is `RIMPE`, also configure the :guilabel:`Profit
   Withholding` percentage.

Puntos de Emisión
-----------------

To configure your printer points, go to :menuselection:`Accounting --> Configuration --> Accounting:
Journals`.

Printer points need to be configured for each type of electronic document that you need. For
example: Customer Invoice, Credit Notes, and Debit Notes

For each printer point, you need to configure the following information:

- :guilabel:`Journal Name`: in this format `[Emission Entity]-[Emission Point] [Document Type]`, for
  example: `001-001 Sales Documents`.
- :guilabel:`Type`: refers to the type of journal, select `Sales`.
- :guilabel:`Use Documents?`: this checkbox is automatically checked, leave it checked.
- :guilabel:`Emission Entity`: configure the establishment number.
- :guilabel:`Emission Point`: configure the printer point.
- :guilabel:`Emission address`: configure the address of the establishment.
- :guilabel:`Default income account`: configure the default income account.
- :guilabel:`Dedicated Credit Note Sequence`: check the checkbox if *Credit Notes* are to be
  generated from this printer point - journal.
- :guilabel:`Short Code`: This is the unique code for the sequence of accounting entries, enter a
  unique 5-digit code, for example: `VT001`

Customer Invoice, Credit Notes and Debit Notes need to use the same journal as the
:guilabel:`Emission Point`, and the :guilabel:`Entity Point` should be unique per journal.

.. image:: ecuador/printer-point.png
   :align: center
   :alt: Configuring a printer point for Ecuador electronic document type of Customer Invoices.

.. note::
   In the :guilabel:`Advanced Settings` tab, check the :guilabel:`Electronic Invoicing` checkbox to
   enable it for Ecuador.

.. seealso::
   :doc:`../accounting/customer_invoices/electronic_invoicing`

Configuracón de Datos Maestros
------------------------------

Plan de Cuentas
~~~~~~~~~~~~~~~

The :doc:`chart of accounts <../accounting/get_started/chart_of_accounts>`
is installed by default as part of the set of data included in the localization module, the accounts
are mapped automatically in Taxes, Default Account Payable, Default Account Receivable.

The chart of accounts for Ecuador is based on the most updated version of Superintendency of
Companies, which is grouped in several categories and is compatible with NIIF accounting.

You can add or delete accounts according to the company's needs.

Productos
~~~~~~~~

In addition to the basic information in your products, you must add the configuration of the
withholding code (tax) that applies.

Go to :menuselection:`Accounting --> Vendors:  Products` under the tab "Purchase"

.. image:: ecuador/products.png
   :align: center
   :alt: Product for Ecuador.

Contactos
~~~~~~~~

Configure la siguiente información cuando cree un contacto:

- Marque la opción :guilabel:`Empresa` en la parte superior si es un contacto con RUC, o marque
  :guilabel:`Individual` si es un contacto con cedula o pasaporte.
- :guilabel:`Nombre
- :guilabel:`Dirección`: :guilabel:`Calle` es un campo obligatorio para confirmar la Factura Electrónica.
- :guilabel:`Número de Identificación`: seleccione un tipo de identificación `RUC`, `Cédula` o `Pasaporte`.
- :guilabel:`Tipo de Contribuyente`: seleccione el Tipo de Contribuyente del ISR del contacto.
- :guilabel:`Teléfono`
- :guilabel:`Correo electrónico`

.. image:: ecuador/contacts.png
   :align: centro
   :alt: Contactos para Ecuador.

.. nota::
   La :guilabel:`SRI Tipo de Contribuyente` tiene dentro la configuración de que IVA y Ganancias
   retenciones se aplicarán al utilizar este contacto en la Factura de Proveedor, y luego crear una retención
   desde allí.
   
Revisión de Impuestos
~~~~~~~~~~~~~~~~~~~~~

Como parte del módulo de localización, los impuestos se crean automáticamente con su configuración y
cuentas financieras relacionadas.

.. image:: ecuador/impuestos.png
   :align: centro
   :alt: Impuestos para Ecuador.

Se han configurado automáticamente las siguientes opciones:

- :guilabel:`Soporte de Impuestos`: a configurar solo en el impuesto IVA, esta opción es útil cuando se
  registrar retenciones de compras.
- :guilabel:`Código ATS`: para configurar sólo en códigos de retención de IVA, es importante cuando
  registrar la retención.
- :guilabel:`Retenciones IRPF`: configurar los códigos del modelo 104 si es un impuesto IVA y configurar los códigos
  del formulario 103 si es una retención de IRPF.
- :guilabel:`Nombre del impuesto`:

  - Para el impuesto IVA, formatee el nombre como: `IVA [porcentaje] (104, [código formulario] [código soporte impuesto] [soporte impuesto
    nombre corto])`.
  - Para el código de retención del impuesto sobre la renta, formatee el nombre como: `Código ATS [Porcentaje de retención] [retención
    nombre]`

Una vez instalado el módulo de Ecuador, los impuestos más comunes se configuran automáticamente. Si usted
necesita crear uno adicional, puede hacerlo, para lo cual debe basarse en la
configuración de los impuestos existentes.

.. image:: ecuador/impuestos-con-impuestos-soporte.png
   :align: center
   :alt: Impuestos con soporte tributario para Ecuador.


Tipos de Documentos Contables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Algunas transacciones contables como *Facturas de clientes* y *Facturas de proveedores* se clasifican por tipos de documentos.
documentos. Estos son definidos por las autoridades fiscales gubernamentales, en este caso por el SRI.

Cada tipo de documento puede tener una secuencia única por diario donde se asigna. Como parte de la
Como parte de la localización, el tipo de documento incluye el país en el que el documento es aplicable.
datos se crean automáticamente cuando se instala el módulo de localización.

La información requerida para los tipos de documentos se incluye por defecto, por lo que el usuario no necesita
rellenar nada.

.. image:: ecuador/document-types.png
   :align: center
   :alt: Document types for Ecuador.












