LIQUIDACION DE COMPRAS
######################

When using Purchase Liquidations, a specific journal must be created, go to
:menuselection:`Accounting --> Configuration --> Accounting:  Journals` and configure the following
information:

- :guilabel:`Journal Name`: in this format `[Emission Entity]-[Emission Point] [Document Type]`, for
  example: `001-001 Withhold`.
- :guilabel:`Type`: refers to the type of journal, select `Miscellaneous`.
- :guilabel:`Purchase Liquidations`: check the checkbox to enable purchase liquidations.
- :guilabel:`Use Documents?`: this checkbox is automatically checked, leave it checked.
- :guilabel:`Emission Entity`: configure the establishment number.
- :guilabel:`Emission Point`: configure the printer point.
- :guilabel:`Emission address`: configure the address of the establishment.
- :guilabel:`Short Code`: This is the unique code for the sequence of accounting entries, enter a
  unique 5-digit code, for example: `RT001`

.. image:: ecuador/purchase-liqudations.png
   :align: center
   :alt: Configuring purchase liquidations for Ecuador electronic document type of Withholding.

.. note::
   In the :guilabel:`Advanced Settings` tab, check the :guilabel:`Electronic Invoicing` checkbox to
   enable the sending of electronic invoicing for the withholding.


Purchase liquidation
~~~~~~~~~~~~~~~~~~~~

The :guilabel:`Purchase liquidation` is an electronic document that, when validated, is sent to SRI.

Companies issue this type of electronic document when they purchase, and the vendor does not issue
an invoice due to one or more of the following cases:

- Services were provided by non-residents of Ecuador.
- Services provided by foreign companies without residency or establishment in Ecuador.
- Purchase of goods or services from natural persons not registered with a RUC, who due to their
  cultural level or hardiness are not able to issue sales receipts or customer invoices.
- Reimbursement for the purchase of goods or services to employees in a dependency relationship
  (full-time employee).
- Services provided by members of collegiate bodies for the exercise of their function.

These types of electronic documents can be created from the :guilabel:`Purchase Order` or manually
from the :guilabel:`Vendor Bills` form view. It must contain the following data:

- :guilabel:`Vendor`: type the vendor's information.
- :guilabel:`Journal`: select the journal for the :guilabel:`Purchase Liquidation` with the correct
  printer point.
- :guilabel:`Document Type`: this is the document type `(03) Purchase Liquidation`
- :guilabel:`Document number`: type the document number (sequence), you will only have to do this
  once, then the sequence will be automatically assigned for the next documents.
- :guilabel:`Payment Method (SRI)`: select how the invoice is going to be paid.
- :guilabel:`Products`: specify the product with the correct taxes.

Once you review the information you can validate the :guilabel:`Purchase Liquidation`.

.. image:: ecuador/purchase-liquidation.png
   :align: center
   :alt: Purchase liquidation for Ecuador.
