**@isdk/ai-tool-fastify**

***

# @isdk/ai-tool-fastify

> ✨ **Fastify HTTP Server Transport for the `ToolFunc` Framework**
> Build decoupled, type-safe, real-time Fastify apps with RPC tools and Pub/Sub events over IPC.

[![npm version](https://img.shields.io/npm/v/@isdk/ai-tool-fastify.svg?style=flat-square)](https://www.npmjs.com/package/@isdk/ai-tool-fastify)
[![Vitest Tests](https://img.shields.io/badge/tests-vitest-green?style=flat-square)](https://vitest.dev/)
[![TypeScript](https://img.shields.io/badge/types-TypeScript-blue?style=flat-square)](https://www.typescriptlang.org/)
[![License: MIT](https://img.shields.io/badge/license-MIT-purple?style=flat-square)](LICENSE)

```bash
npm install @isdk/ai-tool-fastify fastify @isdk/ai-tool
```

Built on [`@isdk/ai-tool`](https://github.com/isdk/ai-tool) — Define reusable, self-documenting functions.

## 🌟 Features

Designed to pair with `@isdk/ai-tool`. Define your business logic once as tools, then call them from any client like local methods.

* ✅ **Fastify Integration** - Expose `ToolFunc` tools over HTTP with a Fastify server.
* ✅ **Automatic Tool Discovery** - Client can fetch a list of all available tools from the server.
* ✅ **RPC (Remote Procedure Call)** - Call server-side tools from the client as if they were local functions.
* ✅ **Type-Safe** - Leverages TypeScript for type-safe tool definitions and calls.

## 🚀 Quick Start

Here is a quick example of how to set up a tool server and call it from a client.

### 1. Create the Server

Create a file `server.ts` and add the following code:

```typescript
import { ServerTools } from '@isdk/ai-tool';
import { FastifyServerToolTransport } from '@isdk/ai-tool-fastify';

// 1. Register a tool on the server side
ServerTools.register({
  name: 'calculator',
  isApi: true,
  func: ({ a, b }: { a: number; b: number }) => {
    return a + b;
  },
});

// 2. Setup the server transport
const serverTransport = new FastifyServerToolTransport();
serverTransport.mount(ServerTools, '/api');

// 3. Start the server
serverTransport.start({ port: 3000 }).then(() => {
  console.log('Server is running on http://localhost:3000');
});
```

### 2. Create the Client

Create a file `client.ts` and add the following code:

```typescript
import { ClientTools, HttpClientToolTransport } from '@isdk/ai-tool';

async function main() {
  // 1. Setup the client transport
  const clientTransport = new HttpClientToolTransport('http://localhost:3000/api');
  ClientTools.setTransport(clientTransport);

  // 2. Load tool definitions from the server
  await ClientTools.loadFrom();

  // 3. Get the dynamically created client-side tool stub
  const calculatorTool = ClientTools.get('calculator');

  // 4. Run the tool. This will trigger an HTTP call.
  const result = await calculatorTool!.run({ a: 40, b: 2 });

  // 5. Assert the result
  console.log('The result is:', result); // The result is: 42
}

main();
```

### 3. Run the code

You can run the server and client using `ts-node` or by compiling them with `tsc` first.

```bash
# In one terminal
npx ts-node server.ts

# In another terminal
npx ts-node client.ts
```

## 🧪 Testing

Run unit tests with mocked Fastify IPC:

```bash
npm test           # run once
npm run test:watch # dev mode
npm run coverage   # generate report
```

## 📚 Docs

- [ToolFunc Core](https://github.com/isdk/ai-tool/blob/main/docs/toolFunc.md)
- [Transports Guide](https://github.com/isdk/ai-tool/blob/main/docs/transport.md)
- [Events Guide](https://github.com/isdk/ai-tool/blob/main/docs/pubsub.md)

## 🤝 Contributing

We ❤️ contributions!

1. Fork → `git clone`
2. Create branch → `git checkout -b feat/your-feature`
3. Commit → `git commit -m 'feat: add XYZ'`
4. Push → `git push origin feat/your-feature`
5. Open PR 🎉

Please ensure tests pass and types are clean.

## 📜 License

MIT © [ISDK](https://github.com/isdk) — See [LICENSE](LICENSE)
