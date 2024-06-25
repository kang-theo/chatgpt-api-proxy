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

## Test

Using Postman.

Server-send Event does not support POST very well, so send GET instead.

- Send a POST request to the route `/api/gpt/chat`
- Set `option`: `encodeURIComponent('{"messages": [ {  "role": "user", "content": "你好，你是谁" }  ]}')`
- Add a header `x-auth-token: xxx` ，defined in `.env`

```bash
/api/gpt/chat?x-auth-token=xxx&option=%7B%22messages%22%3A%20%5B%20%7B%20%20%22role%22%3A%20%22user%22%2C%20%22content%22%3A%20%22%E4%BD%A0%E5%A5%BD%EF%BC%8C%E4%BD%A0%E6%98%AF%E8%B0%81%22%20%7D%20%20%5D%7D
```
