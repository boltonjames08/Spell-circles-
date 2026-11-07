# The Spell Circle

Spell papers, a voice call and a chat for D&D groups. Everyone draws spells on old paper; only the DM can read them.
Players keep their spells in a spell folder that's saved online and opened with their own code.

## Files
- `index.html`: the page
- `server.js`: the server (no extra packages needed)
- `package.json`, `render.yaml`: tell Render how to run it

## Put it online (free, on Render)
1. On GitHub, make a new repository (e.g. `spell-circle`) and upload all the files in this folder.
2. On https://render.com: New → Web Service → pick the repository.
   - Language: **Node** · Build command: `echo no build needed` · Start command: `node server.js` · Instance type: **Free**
3. Wait for "Live", then open your `….onrender.com` address.

## Save spell folders online (do this once)
1. Make a free account at https://upstash.com and create a **Redis** database.
2. On the database page, copy the **REST URL** and **REST token** (the "REST API" section).
3. On Render: your service → **Environment** → add
   - `UPSTASH_REDIS_REST_URL` = the URL
   - `UPSTASH_REDIS_REST_TOKEN` = the token
4. Save. Render restarts the server, and the warning on the folder screen disappears.

Without this, folders and sessions are kept in a file that Render's free plan wipes whenever the server restarts.

## If someone can see people talking but can't hear them
Their network blocks direct voice. A free public voice relay is used automatically. For a more reliable one,
make a free account at https://www.metered.ca/tools/openrelay/ and add `METERED_APP` (your app name, the part
before `.metered.live`) and `METERED_API_KEY` in Render → Environment.

## Updating
Upload the changed files to GitHub (replace the old ones). Render redeploys by itself in a minute or two.
