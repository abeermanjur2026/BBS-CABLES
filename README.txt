BBS CABLES - Master + User Auto Update

MASTER
Upload the contents of MASTER/ to your GitHub repository. Enable GitHub Pages from Settings > Pages > Deploy from branch (main/root).
Master URL expected by USER package:
https://abeermanjur2026.github.io/BBS-CABLES/

USER
Upload USER/ to each separate HTTPS web host if you need separate user links. Keep MASTER_URL in USER/app.js unchanged. Users install the User page as a PWA. When online, it checks Master/version.json. If Master version is newer, UPDATE NOW downloads the released app files into the User service-worker cache and reloads without touching localStorage data.

IMPORTANT
For maximum reliability, the simplest deployment is to let everyone install the Master GitHub Pages URL directly. Separate User copies depend on the hosting platform allowing service workers and cross-origin CORS reads from the Master.

RELEASING A NEW VERSION
1. Edit the Master app files.
2. Change version in MASTER/version.json and MASTER/sw.js cache name, e.g. 1.0.1.
3. Keep USER/app.js V at the currently bundled User version unless you rebuild the User package.
4. Upload changed Master files to GitHub.
5. Users who are online will see UPDATE NOW.

DATA
Saved invoices are stored in browser localStorage and are not deleted by the update process.
