[**@isdk/ai-tool-fastify**](../README.md)

***

[@isdk/ai-tool-fastify](../globals.md) / FastifyServerToolTransport

# Class: FastifyServerToolTransport

Defined in: [ai-tool-fastify/src/fastify-server.ts:9](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L9)

A concrete server transport implementation for Fastify.

## Extends

- `ServerToolTransport`

## Constructors

### new FastifyServerToolTransport()

> **new FastifyServerToolTransport**(`options`?): [`FastifyServerToolTransport`](FastifyServerToolTransport.md)

Defined in: [ai-tool-fastify/src/fastify-server.ts:12](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L12)

#### Parameters

##### options?

`FastifyServerOptions`

#### Returns

[`FastifyServerToolTransport`](FastifyServerToolTransport.md)

#### Overrides

`ServerToolTransport.constructor`

## Properties

### apiRoot

> **apiRoot**: `string`

Defined in: ai-tool/dist/index.d.ts:2374

#### Inherited from

`ServerToolTransport.apiRoot`

***

### options?

> `optional` **options**: `any`

Defined in: ai-tool/dist/index.d.ts:2376

#### Inherited from

`ServerToolTransport.options`

***

### server

> **server**: `FastifyInstance`

Defined in: [ai-tool-fastify/src/fastify-server.ts:10](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L10)

***

### Tools

> **Tools**: *typeof* `ServerTools`

Defined in: ai-tool/dist/index.d.ts:2375

#### Inherited from

`ServerToolTransport.Tools`

## Methods

### \_mount()

> **\_mount**(`Tools`, `apiPrefix`, `options`?): `void`

Defined in: ai-tool/dist/index.d.ts:2377

#### Parameters

##### Tools

*typeof* `ServerTools`

##### apiPrefix

`string`

##### options?

`any`

#### Returns

`void`

#### Inherited from

`ServerToolTransport._mount`

***

### \_start()

> **\_start**(`options`): `Promise`\<`void`\>

Defined in: [ai-tool-fastify/src/fastify-server.ts:74](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L74)

#### Parameters

##### options

###### host?

`string`

###### port

`number`

#### Returns

`Promise`\<`void`\>

#### Overrides

`ServerToolTransport._start`

***

### addDiscoveryHandler()

> **addDiscoveryHandler**(`apiPrefix`, `handler`): `void`

Defined in: [ai-tool-fastify/src/fastify-server.ts:17](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L17)

#### Parameters

##### apiPrefix

`string`

##### handler

() => `any`

#### Returns

`void`

#### Overrides

`ServerToolTransport.addDiscoveryHandler`

***

### addRpcHandler()

> **addRpcHandler**(`serverTools`, `apiPrefix`, `options`?): `void`

Defined in: [ai-tool-fastify/src/fastify-server.ts:25](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L25)

#### Parameters

##### serverTools

*typeof* `ServerTools`

##### apiPrefix

`string`

##### options?

`any`

#### Returns

`void`

#### Overrides

`ServerToolTransport.addRpcHandler`

***

### getRaw()

> **getRaw**(): `any`

Defined in: [ai-tool-fastify/src/fastify-server.ts:89](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L89)

#### Returns

`any`

#### Overrides

`ServerToolTransport.getRaw`

***

### mount()

> **mount**(`Tools`, `apiRoot`?, `options`?): `any`

Defined in: ai-tool/dist/index-BCco-g\_I.d.ts:1143

#### Parameters

##### Tools

*typeof* `ToolFunc`

##### apiRoot?

`string`

##### options?

`any`

#### Returns

`any`

#### Inherited from

`ServerToolTransport.mount`

***

### setApiRoot()

> **setApiRoot**(`apiRoot`): `void`

Defined in: ai-tool/dist/index-BCco-g\_I.d.ts:1142

#### Parameters

##### apiRoot

`string`

#### Returns

`void`

#### Inherited from

`ServerToolTransport.setApiRoot`

***

### start()

> **start**(`options`?): `Promise`\<`any`\>

Defined in: ai-tool/dist/index.d.ts:2378

Starts the transport layer, making it listen for incoming connections.

#### Parameters

##### options?

`any`

Protocol-specific options (e.g., { port, host }).

#### Returns

`Promise`\<`any`\>

#### Inherited from

`ServerToolTransport.start`

***

### stop()

> **stop**(`force`?): `Promise`\<`void`\>

Defined in: [ai-tool-fastify/src/fastify-server.ts:85](https://github.com/isdk/ai-tool-fastify.js/blob/689f67e7cbe318f53608fddbed5977da91bb03d4/src/fastify-server.ts#L85)

#### Parameters

##### force?

`boolean`

#### Returns

`Promise`\<`void`\>

#### Overrides

`ServerToolTransport.stop`
