RETENCIONES
###########

DIARIO CONTABLE
===============

Retención
---------

A Withholding Journal must be defined, go to go to :menuselection:`Accounting --> Configuration -->
Accounting:  Journals` where you need to configure the following information:

- :guilabel:`Journal Name`: in this format `[Emission Entity]-[Emission Point] [Document Type]`, for
  example: `001-001 Withholding`.
- :guilabel:`Type`: refers to the type of journal, select `Miscellaneous`.
- :guilabel:`Withhold Type`: Configure Purchase Withholding.
- :guilabel:`Use Documents?`: this checkbox is automatically checked, leave it checked.
- :guilabel:`Emission Entity`: configure the establishment number.
- :guilabel:`Emission Point`: configure the printer point.
- :guilabel:`Emission address`: configure the address of the establishment.
- :guilabel:`Default account`: configure the default income account.
- :guilabel:`Short Code`: This is the unique code for the sequence of accounting entries, enter a
  unique 5-digit code, for example: `RT001`

.. image:: ecuador/withhold.png
   :align: center
   :alt: Configuring withholding for Ecuador electronic document type of Withholding.

.. note::
   In the :guilabel:`Advanced Settings` tab, check the :guilabel:`Electronic Invoicing` checkbox to
   enable the sending of electronic invoicing for the withholding.


Retención de cliente
~~~~~~~~~~~~~~~~~~~~

The :guilabel:`Customer withholding` is a non-electronic document for your company, this document is
issued by the client in order to apply a withholding to the sale.

It is necessary to have a validated (posted) invoice in order to register a customer withholding. On
the invoice there is a button named :guilabel:`Add Withhold`,  click on this button to be directed
to the :guilabel:`Customer withholding` form, then complete the following information:

- :guilabel:`Document Number`: type the withholding number.
- :guilabel:`Withhold Lines`: select the taxes that the customer is withholding.

Before validating the withholding, review that the amounts for each tax are the same as the original
document.

.. image:: ecuador/customer-withhold.png
   :align: center
   :alt: Customer withhold for Ecuador.


Retención de proveedor
~~~~~~~~~~~~~~~~~~~~~~

The :guilabel:`Purchase withholding` is an electronic document that, when validated, is sent to SRI.

It is necessary to have an invoice in a validated state in order to register a :guilabel:`Purchase
withholding`. On the invoice, there is a button named :guilabel:`Add Withhold`, click on this button
to be directed to the :guilabel:`Withholding` form, then complete the following information:

- :guilabel:`Document number`: type the document number (sequence), you will only have to do this
  once, then the sequence will be automatically assigned for the next documents.
- :guilabel:`Withhold lines`: The taxes appear automatically according to the configuration of
  products and vendors, you should review if the taxes and tax support are correct, and, if it is
  not correct, you can edit and select the correct taxes and tax support.

Once you review the information you can validate the :guilabel:`Withholding`.

.. image:: ecuador/purchase-withhold.png
   :align: center
   :alt: Purchase withhold for Ecuador.

.. note::
   You can't change the tax support for one that was not included in the configuration of the taxes
   used on the :guilabel:`Vendor Bill`. To do so, go to the tax applied on the :guilabel:`Vendor
   Bill` and change the :guilabel:`Tax Support` there.

A withholding tax can be divided into two or more lines, this will depend on whether two or more
withholdings percentages apply.

.. example::
   The system suggests a VAT withholding of 30% with tax support 01, you can add your VAT
   withholding of 70% in a new line with the same tax support, the system will allow you as long as
   the total of the bases matches the total from the :guilabel:`Vendor Bill`.

