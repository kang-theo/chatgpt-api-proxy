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

- Send a GET request to the route `/api/gpt/chat`
- Set `option`: `{"messages": [ { "role": "user", "content": "How are you?" } ]}`
- Add a header `x-auth-token: xxx` ，defined in `.env`

```bash
$ip:$port/api/gpt/chat?x-auth-token=xxx&option={"messages": [ { "role": "user", "content": "How are you?" } ]}
```

## Deploy

- Submitting deploy branch to GitHub will trigger the deployment of "gpt-api-proxy" to AWS EC2 (ci.yml).
- Set the environment variables in `.env`
