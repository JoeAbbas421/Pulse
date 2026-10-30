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
