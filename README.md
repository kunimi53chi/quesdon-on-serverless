# quesdon

SNS of communicate with question (like ["ask.fm"](https://ask.fm/)) for Mastodon. This repository is forked origin and changes structure to serverless architecture (WIP) .

LICENSE: [AGPL 3.0](LICENSE)

## how to run

required: latest version Node.js, MongoDB

```sh
yarn install
yarn build
MONGODB_URL=mongodb://localhost/quesdon BACK_PORT=3000 yarn start
```

## How to develop

### Run development

1. `cp .env.development .env`
2. `yarn dev`
3. open `<http://localhost:8080>`

### File Structure

- `src/`: All source
    - `server/`: Server-side source
        - `api/`: about API
        - `db/`: Database model
        - `utils/`: use anywhere
    - `client/`: client source
- `views/`: template see server-side (written in pug)