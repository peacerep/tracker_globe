## Global Peace and Conflict 

<img src="globe_peace_min.jpg"/>

This is a [`Svelte`] project scaffolded with [`Vite`]. It includes a deployment setup using [`gh-pages`] to publish the built site to GitHub Pages.

The result is the Tracker globe: https://peacerep.github.io/tracker_globe/ and also onrender version: https://globe-tracker.onrender.com/ 

Both should get updated once deploy (see instructions below), but onrender may need a manual update if does not auto update. 

### Prerequisites [for local install]

- [`Node.js`] 
- [`Yarn`] installed globally

### Installation

#### Locally

`yarn install`

#### Docker
`docker run --rm -it -v "${PWD}:/app" -w /app node:22 yarn install`

### Development
#### Local
`yarn dev` 

#### Docker
`docker run --rm -it -v "${PWD}:/app" -w /app -p 5173:5173 node:22 sh -lc "yarn dev --host 0.0.0.0"`

Open http://localhost:5173

### Build

#### Locally
`yarn build`

#### Docker 

`docker run --rm -it -v "${PWD}:/app" -w /app node:22 yarn build`

### Deployment

#### Local

`yarn deploy`

#### Docker
`docker run --rm -it -v "${PWD}:/app" -w /app node:22 yarn deploy`

### Monthly update

1. Replace 3 csv and 1 json file in public/data with monthly updates:
`agt_point_data.csv`, `country_data.csv`, `filled_polygon_data_5.csv`, `info_section.json`

2. Check if all is good with:
```bash
	yarn dev
```

3. Build: 
```bash
	yarn build
```

4. Deploy:
```bash
	yarn deploy
```

5. Git:
```bash
git add .
git commit -m "message"
git push
```


### Handy note
- If need to update legend for year edit `src/App.svelte`
- May need PAT from github to build and deploy (for the peacerep organisation - not personal account)

