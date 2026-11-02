# Pulse web app

Put this folder on any HTTPS host (GitHub Pages works and is free), open it in Safari on your iPhone, tap Share, then **Add to Home Screen**.

## Connect your real Fitbit Air data (one time, about 10 minutes)

1. Open [Google Cloud Console](https://console.cloud.google.com/) and create a project.
2. Go to **APIs & Services > Library**, search for **Google Health API** and enable it.
3. Go to **OAuth consent screen**: choose External, keep it in Testing, and add your own Google account under Test users. Add these scopes:
   - `.../auth/googlehealth.activity_and_fitness.readonly`
   - `.../auth/googlehealth.health_metrics_and_measurements.readonly`
   - `.../auth/googlehealth.sleep.readonly`
   - `.../auth/googlehealth.irn.readonly`
   - `.../auth/googlehealth.profile.readonly`
4. Go to **Credentials > Create credentials > OAuth client ID**, type **Web application**.
   - Authorized JavaScript origin: your site's address, for example `https://yourname.github.io`
   - Authorized redirect URI: the full page address, for example `https://yourname.github.io/pulse/`
5. Copy the client ID. In Pulse, open the **You** tab, paste it, and tap **Connect Google Health**. Sign in with the Google account your Fitbit Air uses.

After the first sign-in, Pulse quietly renews your Google sign-in when it expires (about every hour). The You tab's Data inspector shows what each Google data type returned, so any empty tile can be fixed.

## Claude coach (the Claude tab)

Claude reads a summary of your numbers and gives you a daily checkup (how you're doing, today's plan, anything to watch) and answers questions about your sleep, heart and training. Every workout result also has an **Ask Claude about this session** button.

- **Best: add your own Anthropic API key** (Claude tab → Connect Claude). Get one at https://console.anthropic.com/settings/keys and add a little credit under Billing. With a key, Claude runs inside Pulse and your checkup appears automatically the first time you open Pulse each day. A checkup or answer costs roughly 3 to 6 US cents.
- **No key:** the buttons open the Claude app with your data (copied to the clipboard if it's long), so you can use your normal Claude plan.
- The key and your data stay on your phone. Only the summary goes to Anthropic, straight from your phone. Claude is a coach, not a doctor.
