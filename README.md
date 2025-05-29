 [![Discord](https://dcbadge.vercel.app/api/server/xWRaCDBtW4?style=flat)](https://discord.gg/xWRaCDBtW4)

# Amazon Bedrock Agent Demo

A Simple Open Enrollment Voice Agent built with the [Deepgram Agent API](https://developers.deepgram.com/docs/voice-agent) and [Amazon Bedrock](https://aws.amazon.com/bedrock/).

This demo showcases:

* Amazon Bedrock LLM Configuration
* Amazon Bedrock LLM Function Calling
* Deepgram Agent Configuration
* A basic browser agent
* Websocket Interface Implementation to:
  * Send browser microphone audio
  * Receive audio response


## Getting an API Key

🔑 To access the Deepgram API you will need a [free Deepgram API Key](https://console.deepgram.com/signup?jump=keys).


## Quickstart

### Install Dependencies

In the root of the repo run:

```bash
npm install
```

### Add your Deepgram API Key

In [config.js](./js/config.js) add your API Key.

> SECURITY WARNING: Do not commit you API Key to GitHub.

```js
  let ws = new WebSocket("wss://agent.deepgram.com/agent", ["token", "<your-api-key-here>"]);
```

## Start the HTTP Server

In the root of the repo run:

```bash
npm start
```

### Set your Amazon Bedrock LLM Provider URL

> See The [Deepgram Voice Agent LLM Client Proxy Repo](https://github.com/deepgram-devs/deepgram-voice-agent-client-llm-proxy) for a Chat Completion Proxy Server you can run locally using NGROK.

In [config.js](./js/config.js) set your Provider URL and key

```javascript

        agent: {
            ...baseConfig.agent,
            think: {
                provider: {
                    type: "bedrock",
                    url: "your-bedrock-llm-url",
                    key: "your-bedrock-key",
                },
                model: "your-bedrock-model",
                instructions: ` Your LLM instructions and prompts`,

            }
        },
```


## Development and Contributing

Interested in contributing? We ❤️ pull requests!

To make sure our community is safe for all, be sure to review and agree to our
[Code of Conduct](./.github/CODE_OF_CONDUCT.md). Then see the
[Contribution](./.github/CONTRIBUTING.md) guidelines for more information.

## Getting Help

We love to hear from you so if you have questions, comments or find a bug in the
project, let us know! You can either:

- [Open an issue in this repository](https://github.com/deepgram/amazon-bedrock-agent-demo/issues/new)
- [Join the Deepgram Github Discussions Community](https://github.com/orgs/deepgram/discussions)
- [Join the Deepgram Discord Community](https://discord.gg/xWRaCDBtW4)

[license]: LICENSE.txt



