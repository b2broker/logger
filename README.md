# @kauai/logger ![CI Status](https://github.com/b2broker/logger/workflows/CI/badge.svg) [![version](https://img.shields.io/github/package-json/v/b2broker/logger?style=plastic)](https://github.com/b2broker/logger) [![Known Vulnerabilities](https://snyk.io/test/github/b2broker/logger/badge.svg)](https://snyk.io/test/github/b2broker/logger) [![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg)](https://github.com/prettier/prettier) [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release) [![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-yellow.svg)](https://conventionalcommits.org) ![GitHub top language](https://img.shields.io/github/languages/top/b2broker/logger) ![node version](https://img.shields.io/node/v/@kauai/logger) ![npm downloads](https://img.shields.io/npm/dt/@kauai/logger) ![License](https://img.shields.io/github/license/b2broker/logger)

A simple logger (based on [`pino`](https://github.com/pinojs/pino)).

By default, the logging level is equal to the value of the `KAUAI_LOG_LEVEL` environmental variable.

```bash
KAUAI_LOG_LEVEL=trace
```

## Installation

```bash
npm install @kauai/logger
```

## Usage

```javascript
import { Logger } from "@kauai/logger";
const logger = new Logger({ level: Logger.getLevel("OTHER_ENV_NAME") });
```

or using the default import

```javascript
import log from "@kauai/logger";
```

- `.fatal()`

```javascript
log.fatal("Bad error. Exiting...", { id: 1, someinfo: { a: 2 } });
```

- `.error()`

```javascript
try {
  doSomething();
} catch (error) {
  log.error("Something bad happened in the `doSomething`", { error });
}
```

- `.warn()`

```javascript
if (connection) {
  workWithConnection();
} else {
  log.warn("The connection has not been established", { reason });
}
```

- `.info()`

```javascript
server.on("listening", (port) => {
  log.info(`The server is listening`, { port });
});
```

- `.debug()`

```javascript
websocket.on("message", (message) => {
  log.debug("Received a message", { message });
});
```

- `.trace()`

```javascript
log.trace("Array length", { length: arr.length });
```
