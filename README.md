🚀 Cloudflare Smart Development Mode & Auto Cache Purger (PHP)

Automatically enable Cloudflare Development Mode and purge cache when your files change.

Built for developers who want instant updates, zero manual cache clearing, and a smoother workflow when working behind Cloudflare.

✨ Features
⚡ Auto Cache Purge
Automatically clears Cloudflare cache when recent file changes are detected
🛠 Smart Development Mode
Enables Cloudflare Development Mode to bypass caching during active development
📂 Recursive File Monitoring
Scans all directories and subdirectories using recursive glob
🧠 Smart Trigger Logic
Prevents duplicate API calls using a local state file
⏱ Cron Ready
Designed to run every minute with minimal server load
🔒 Lightweight & Dependency-Free
Pure PHP (no frameworks required)
📦 Use Cases
Local → live deployments
Git / FTP / rsync updates
WordPress theme/plugin development
Static site updates
Agency workflows managing multiple sites
⚙️ Requirements
PHP 7.0+
cURL enabled
Cron access
Cloudflare API Token
Cloudflare Zone ID
🔧 Installation
1. Upload the script

Upload the PHP file to your server:

cloudflare-devmode-cache-clear.php
2. Configure the script

Edit the config section:
<pre>
$watchDir   = __DIR__;
$maxAge     = 300;

$cloudflareApiToken = 'YOUR_API_TOKEN';
$cloudflareZoneId   = 'YOUR_ZONE_ID';
</pre>

3. Set directory to monitor

Example:

$watchDir = '/home/user/public_html';
4. Add cron job

Run every minute:

* * * * * /usr/bin/php /full/path/to/cloudflare-devmode-cache-clear.php >/dev/null 2>&1
5. Done ✅

The script will now:

Detect file changes within the last 5 minutes
Enable Development Mode
Purge Cloudflare cache
🔄 How It Works
Recursively scans all files
Finds the most recently modified file
Checks if modified within last X seconds (default: 300)
Triggers:
Development Mode ON
Cache Purge
Stores state to prevent duplicate triggers
🔐 Cloudflare API Permissions

Your API token should include:

Zone → Settings → Edit
Zone → Cache Purge → Edit
(Optional) Zone → Read
📁 File Structure
/project
 ├── cloudflare-devmode-cache-clear.php
 └── cloudflare-devmode-cache-clear.state.json (auto-generated)
🧪 Testing

Run manually:

php cloudflare-devmode-cache-clear.php

Then modify a file and re-run to confirm it triggers.

⚠️ Important Notes
Do NOT expose your API token publicly
Store script outside public web root if possible
Ensure write permissions for state file
Cron must be active for automation
🛠 Customization Ideas
Filter file types (*.php, *.css, etc.)
Partial cache purge instead of full purge
Email notifications on trigger
Webhook integrations
Deployment hooks
💰 License

This project is licensed for commercial use.

If you purchased this product, you are allowed to:

Use it in personal and client projects
Modify the code

You may NOT:

Resell or redistribute the original source code
🙌 Support

For support, contact:

support@example.com

⭐ If You Like This Project

Give it a ⭐ on GitHub — it helps a lot!
