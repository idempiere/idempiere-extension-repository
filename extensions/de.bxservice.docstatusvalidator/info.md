# Document Status Validator

**Summary:** Lets you define SQL conditions that block a document status change. When a condition
matches, the status change is refused and the user is shown a message explaining what to fix.

## 🚀 Features

* **SQL-defined validations:** Express a rule as a WHERE clause over the document's own table — no
  Java, no deployment, configured entirely in the application.
* **Any document, any transition:** Applies to any table with a `DocStatus` column, targeted at the
  document event you choose (prepare, complete, close, void, …).
* **Actionable error messages:** Each validation carries its own message, so the user is told what
  is wrong and what to do rather than seeing a generic failure.
* **Translatable:** Messages are held in a translation table, so each user sees the message in
  their own language.
* **Tenant-level configuration:** Rules are data, so different tenants can enforce different
  policies on the same installation.

## ⚙️ Compatibility

* **iDempiere Version:** 14
* **Java Version:** 17+
* **Database:** PostgreSQL, Oracle

## 📦 Database Changes

* **System PackIn:** installs an incremental 2Pack into the System tenant (`2Pack_1.0.0` followed
  by `2Pack_1.0.1`) under entity type **`BAY`**. It creates:
  * table `BXS_DocValidation` and its translation table `BXS_DocValidation_Trl`;
  * the window and menu entry **Document Status Validation**;
  * the validation rules *AD_Table having DocStatus* and *DocumentEventValidator*.
* **No raw SQL** is executed by the package — all changes are dictionary records.
* No tenant PackIn or CSV import is required.

## 🛠 Usage & Configuration

After installation, open **Document Status Validation** from the menu and create one record per
rule:

* pick the **table** the rule applies to (the list is limited to tables that have a `DocStatus`
  column);
* pick the **document event** the rule guards;
* write the **SQL condition** that identifies records which must be blocked;
* write the **message** shown to the user when the condition matches.

Full documentation, including screenshots and worked examples:

* Wiki: [Plugin: Document Status Validator](https://wiki.idempiere.org/en/Plugin:_Document_Status_Validator)
* Video walkthrough: [https://youtu.be/4Q6i1OOpIDI](https://youtu.be/4Q6i1OOpIDI)

## 👤 Author / Support

* **Developer:** Diego Ruiz — BX Service GmbH
* **Source Code:** [https://github.com/bxservice/de.bxservice.docstatusvalidator](https://github.com/bxservice/de.bxservice.docstatusvalidator)
* **Licence:** GPL-2.0-or-later
* **Issue Tracker:** [https://github.com/bxservice/de.bxservice.docstatusvalidator/issues](https://github.com/bxservice/de.bxservice.docstatusvalidator/issues)
* **Community:** questions and feedback in the iDempiere forums
