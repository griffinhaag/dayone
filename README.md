# DayONE

A help site for new Dunwoody College students. It collects short YouTube tutorials so students can fix common setup problems on their first day, sorted by platform (Windows, Mac, Linux) and topic.

Capstone project for Web Development and Database Engineering at Dunwoody College of Technology.
- **Griffin Haag**: programming
- **Lucas Kells**: cloud deployment (AWS S3 static hosting)

## Features

- Video library filtered by platform and category, with titles and thumbnails pulled from the YouTube Data API
- Register and log in, with passwords hashed in the browser using SHA-256
- Admin dashboard for adding videos by URL and managing platforms and categories
- Fully static, so it runs from S3 or by opening `index.html`

Login is simulated on the client using `Members/users.json`, since the brief called for a static site. It's a demo, not real authentication.

## Running it

1. Copy `js/config.example.js` to `js/config.js` and add a YouTube Data API v3 key. `config.js` is gitignored so the key isn't committed.
2. Open `index.html` in a browser, or serve the folder with any static server.
3. Register an account. To try the admin tools, set that user's `"role"` to `"admin"` in `Members/users.json` and log in again.

## Layout

```
index.html            Video library
css/                  Styles
js/
  script.js           Loads and filters videos
  auth.js             Login/session helpers
  userDatabase.js     Reads and writes the user list
  admin.js            Admin dashboard logic
  config.example.js   Template for the API key config
credentials/          Login, register, user, and admin pages
Members/users.json    Demo user store
Videos/               Video list (youtube_videos.json)
```

Sources and attributions are in [REFERENCES.md](REFERENCES.md).
