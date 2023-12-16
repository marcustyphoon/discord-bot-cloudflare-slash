# /create with Cloudflare Workers

A [slash-create](https://npm.im/slash-create) template, using [Cloudflare Workers](https://workers.cloudflare.com).

## Getting Started

Install dependencies using npm or yarn:

```sh
npm install
```

Run `wrangler login` to login to your Cloudflare account with OAuth:

```sh
wrangler login
```

### Filling in secrets

You can enter in environment secrets with `wrangler secret put`, here are the keys that are required to run this:

```sh
npx wrangler secret put DISCORD_APP_ID
npx wrangler secret put DISCORD_PUBLIC_KEY
npx wrangler secret put DISCORD_BOT_TOKEN
```

### Development

To run this locally, copy `.env.example` to `.dev.vars` and fill in the variables, then you can run `npm run dev` (or `yarn dev`) to start a local dev environment and use something like ngrok to tunnel it to a URL.

To sync commands in the development environment, copy `.env.example` to `development.env` and fill in the variables, then run `npm run sync:dev` (or `yarn sync:dev`).

> Note: When you create a command, make sure to include it in the array of commands in `./src/commands/index.ts`.

### Production

To sync to production, copy `.env.example` to `.env` and fill in the variables, then run `npm run sync`. To publish code to a worker, run `npm run deploy`.
