
Introducción
============

With the Ecuadorian localization you can generate electronic documents with its XML, Fiscal folio,
with electronic signature and direct connection to tax authority SRI.

The supported documents are Invoices, Credit Notes, Debit Notes, Purchase Liquidations and
Withholds.

The localization also Includes automations to easily predict the withholding tax to be applied to
each purchase invoice.

.. seealso::
   - `App Tour - Localización de Ecuador <https://www.youtube.com/watch?v=BQOXVSDeeK8>`_
   - `Smart Tutorial - Localización de Ecuador <https://www.odoo.com/slides/smart-tutorial-localizacion-de-ecuador-170>`_

Glossary
--------

Here are some terms that are essential on the Ecuadorian localization:

- **SRI**: meaning *Servicio de Rentas Internas*, the government organization that enforces pay of
  taxes in Ecuador.
- **EDI**: stands for *Electronic Data Interchange*, which refers to the sending of Electronics
  Documents.
- **RIMPE**: stands for *Regimen Simplificado para Emprendedores y Negocios*, the type of taxpayer
  qualified for SRI.

Configuración
=============

Instalación de los Módulos
-------------------------

:ref:`Install <general/install>` the following modules to get all the features of the Ecuadorian
localization:

.. list-table::
   :header-rows: 1
   :widths: 25 25 50

   * - Name
     - Technical name
     - Description
   * - :guilabel:`Localizacón Base`
     - `l10n_ec_base`
     - The default :doc:`fiscal localization package <../fiscal_localizations>`, adds accounting
       characteristics for the Ecuadorian localization, which represent the minimum configuration
       required for a company to operate in Ecuador according to the guidelines set by the
       :abbr:`SRI (servicio de rentas internas)`. The module's installation automatically loads:
       Chart of Accounts, taxes, documents types, tax support types. Additionally, the generation of
       forms 103 and 104 are automatic.
   * - :guilabel:`Documentos Electrónicos`
     - `l10n_ec_edi`
     - Includes all the technical and functional requirements to generate and validate
       :doc:`Electronics Documents
       <../accounting/customer_invoices/electronic_invoicing>`, based on the Technical
       documentation published by the SRI. The authorized documents are: Invoices, Credit Notes,
       Debit Notes, Withholdings and Purchase liquidations.
       * - :guilabel:`Organización Territorial`
     - `l10n_ec_ote`
     - Includes all the technical and functional requirements to generate and validate
       :doc:`Electronics Documents
       <../accounting/customer_invoices/electronic_invoicing>`, based on the Technical
       documentation published by the SRI. The authorized documents are: Invoices, Credit Notes,
       Debit Notes, Withholdings and Purchase liquidations.
       * - :guilabel:`Retenciones Venta/Compra`
     - `l10n_ec_ote`
     - Includes all the technical and functional requirements to generate and validate
       :doc:`Electronics Documents
       <../accounting/customer_invoices/electronic_invoicing>`, based on the Technical
       documentation published by the SRI. The authorized documents are: Invoices, Credit Notes,
       Debit Notes, Withholdings and Purchase liquidations.
           * - :guilabel:`Guias de Remisión`
     - `l10n_ec_ote`
     - Includes all the technical and functional requirements to generate and validate
       :doc:`Electronics Documents
       <../accounting/customer_invoices/electronic_invoicing>`, based on the Technical
       documentation published by the SRI. The authorized documents are: Invoices, Credit Notes,
       Debit Notes, Withholdings and Purchase liquidations.

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

To upload your information for electronic documents go to :menuselection:`Accounting -->
Configuration --> Settings` and search for :command:`Ecuadorian Localization`.

Configure the next information:

- :guilabel:`Company legal name`
- :guilabel:`Use production servers`: check the checkbox if your company is going to do electronic
  documents in the production environment. If you want to use the testing environment for electronic
  documents then keep the checkbox unchecked.
- :guilabel:`Regime`: select if your company is in General Regular or is qualified as RIMPE.
- :guilabel:`Forced to keep accounting books`: check the checkbox if your company has this
  condition.
- :guilabel:`Default taxes for withholdings`
- :guilabel:`Issue withholds`: check the checkbox if your company is going to do electronic
  withholds.
- :guilabel:`Withhold consumibles`: put the code of the withholding for when you buy goods.
- :guilabel:`Withhold services`: put the code of the withholding for when you buy services.
- :guilabel:`Withhold credit card`: put the code of the withholding for when you buy with credit
  card
- :guilabel:`Withhold agent number`: put the company withholding agent resolution number, if
  applicable for your company.
- :guilabel:`Electronic Certificate File`: upload electronic certificate and password, then save it.
- :guilabel:`Special tax contributor number`: if your company is qualified as a special taxpayer,
  fill out this field with it's corresponding tax contributor number.

.. image:: ecuador/electronic-signature.png
   :align: center
   :alt: Electronic signature for Ecuador.

.. note::
   When configuring the withholdings in the configuration menu, these suggested withholdings are
   only for domestic suppliers when no withholdings are setup on their *Taxpayer Type*. Moreover,
   the Credit Card withholding set up is always used when a Credit or Debit Card SRI Payment Metho
   is used.

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

Printer points
--------------

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

Configure the next information when you create a contact:

- Check the :guilabel:`Company` option on top if it is a contact with RUC, or check
  :guilabel:`Individual` if it is a contact with cedula or passport.
- :guilabel:`Name`
- :guilabel:`Address`: :guilabel:`Street` is a required field to confirm the Electronic Invoice.
- :guilabel:`Identification Number`: select an identification type `RUC`, `Cedula`, or `Passport`.
- :guilabel:`Taxpayer Type`: select the contact's SRI Taxpayer Type.
- :guilabel:`Phone`
- :guilabel:`Email`

.. image:: ecuador/contacts.png
   :align: center
   :alt: Contacts for Ecuador.

.. note::
   The :guilabel:`SRI Taxpayer Type` has inside the configuration of which VAT and Profit
   withholding will apply when you use this contact on Vendor Bill, and then create a withholding
   from there.

Revisión de Impuestos
~~~~~~~~~~~~~~~~~~~~~

As part of the localization module, taxes are automatically created with its configuration and
related financial accounts.

.. image:: ecuador/taxes.png
   :align: center
   :alt: Taxes for Ecuador.

The following options have been automatically configured:

- :guilabel:`Tax Support`: to be configured only in the IVA tax, this option is useful when you
  register purchase withholdings.
- :guilabel:`Code ATS`: to be configured only for income tax withholding codes, it is important when
  you register the withholding.
- :guilabel:`Tax Grids`: configure the codes of 104 form if it is a IVA tax and configure the codes
  of 103 form if it is a  income tax withholding code.
- :guilabel:`Tax Name`:

  - For IVA tax, format the name as: `IVA [percent] (104, [form code] [tax support code] [tax support
    short name])`
  - For income tax withholding code, format the name as: `Code ATS [Percent of withhold] [withhold
    name]`

Once the Ecuador module is installed, the most common taxes are automatically configured. If you
need to create an additional one, you can do so, for which you must base yourself on the
configuration of the existing taxes.

.. image:: ecuador/taxes-with-tax-support.png
   :align: center
   :alt: Taxes with tax support for Ecuador.

Tipos de Documentos Contables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Some accounting transactions like *Customer Invoices* and *Vendor Bills* are classified by document
types. These are defined by the government fiscal authorities, in this case by the SRI.

Each document type can have a unique sequence per journal where it is assigned. As part of the
localization, the document type includes the country on which the document is applicable; also the
data is created automatically when the localization module is installed.

The information required for the document types is included by default so the user does not need to
fill anything there.

.. image:: ecuador/document-types.png
   :align: center
   :alt: Document types for Ecuador.











