# iDempiere Log Viewer

**Summary:** A browser page for the iDempiere server log directory. Administrators can read, download, rotate, and delete trace logs without opening the server filesystem.

## 🚀 Features

* **Log browser:** Lists `.log` files under the server `log` directory, newest name first, and renders the selected file as a time-and-message table.
* **Light and dark theme:** Switch the page theme in the toolbar.
* **Download:** Save an individual log file from the browser.
* **Rotate and delete:** Rotate the trace log, or delete trace logs, using the same server operations as the iDempiere monitor.
* **Large-file guard:** Files larger than the configured limit are not rendered in the page. Download them instead.
* **Access control:** Requires an iDempiere user who is a System Administrator, or who already has URL form access to `/idempiereMonitor`. Supports the same optional SSO path as the monitor.

## ⚙️ Compatibility

* **iDempiere Version:** 14
* **Java Version:** 17+
* **Database:** PostgreSQL, Oracle

The plug-in does not talk to the database except to read optional System Configurator values and to authenticate the user. It imports `javax.servlet` 4.x and sets `Jetty-Environment: ee8`.

## 📦 Database Changes

None. This extension ships no 2Pack and creates no dictionary records.

The size limit is an optional System Configurator. When that record is absent, the plug-in uses 50 MB.

## 🛠 Usage & Configuration

After installation, open `https://<your-server>/log-viewer`.

Sign in with HTTP Basic authentication (or SSO, when `ENABLE_SSO_IDEMPIERE_MONITOR` is enabled). The user must be a System Administrator, or have URL form access to `/idempiereMonitor`.

Optional size limit:

1. Open **System Configurator**.
2. Create a record named `LOG_VIEWER_LIMIT_SIZE`.
3. Set the value in bytes. The default, used when the record does not exist, is `50000000` (50 MB).

The page reads files from the `log` directory under the iDempiere home (`Ini.getAdempiereHome()`). Rotate writes a new trace log. Delete clears trace logs on the server.

![Log viewer, light and dark theme](assets/log-viewer.jpg)

## 👤 Author / Support

* **Developer:** [Zuhri Utama](https://github.com/uthadehikaru) (Reka Estu Digital)
* **Source Code:** [https://github.com/uthadehikaru/idempiere-log-viewer](https://github.com/uthadehikaru/idempiere-log-viewer) (tag [`1.0.1`](https://github.com/uthadehikaru/idempiere-log-viewer/tree/1.0.1), commit `b82423d047cd18386b5206158c6318bcebece018`)
* **Licence:** GPL-2.0-only
* **Issue Tracker:** [https://github.com/uthadehikaru/idempiere-log-viewer/issues](https://github.com/uthadehikaru/idempiere-log-viewer/issues)
