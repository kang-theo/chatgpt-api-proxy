# chatgpt-api-proxy

A proxy of OpenAI API based on node.

## Run
`.env.example` -> `.env`

```bash
npm install

# development
npm run dev

# production
npm run prod
npx pm2 list
npx pm2 restart <id>
npx pm2 stop <id>
npx pm2 delete <id>
```
