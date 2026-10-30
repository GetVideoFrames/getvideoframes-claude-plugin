# GetVideoFrames for Claude

GetVideoFrames connects Claude to frame extraction for public videos. It creates and monitors extraction jobs, shows the extracted frames, and lets Claude look at a single frame so it can describe or analyze it.

## Supported sources

- YouTube
- Instagram
- TikTok
- Facebook
- X
- Vimeo
- Google Drive
- Direct MP4, MOV and WebM links

Videos must be publicly accessible. Availability can vary when a source platform restricts access. GetVideoFrames extracts frames only; it does not transcribe audio (for transcripts, use [GetTranscribe](https://www.gettranscribe.ai)).

## Install

**claude.ai, Claude Desktop and Cowork:** open the [Claude directory](https://claude.ai/directory), search for GetVideoFrames and add it. Plugins added on claude.ai also load in Claude Code.

**Claude Code from this repository:**

```text
/plugin marketplace add GetVideoFrames/getvideoframes-claude-plugin
/plugin install getvideoframes@getvideoframes
```

Claude connects to `https://mcp.getvideoframes.com/mcp`. On first use, sign in through the GetVideoFrames OAuth authorization screen with an API key from your [GetVideoFrames developer dashboard](https://getvideoframes.com/developers/). This plugin does not contain API keys or other secrets.

## Use it

Ask Claude to extract frames from a supported public video URL. For example:

```text
Extract a frame every 5 seconds from https://www.youtube.com/watch?v=jNQXAC9IVRw and show them to me.
```

You can also ask it to list your extraction jobs, open one by ID, make a quick 6-frame preview, or describe what a specific frame shows.

## Local testing

```bash
claude --plugin-dir /absolute/path/to/getvideoframes-claude-plugin
```

In the Claude Code session, use `/mcp` to complete authorization when prompted. The skill is available as `/getvideoframes:getvideoframes-frame-workflow`.

## Security and privacy

The plugin runs no local code. It only points Claude at the hosted GetVideoFrames MCP server at `https://mcp.getvideoframes.com/mcp`, which authenticates each user separately with OAuth. The video URLs you ask Claude to process are sent to GetVideoFrames to fulfill those requests. Do not add API keys to this repository.

Privacy policy: https://getvideoframes.com/privacy/
Terms: https://getvideoframes.com/terms/
Docs: https://getvideoframes.com/integrations/claude/

## License

MIT. See [LICENSE](LICENSE).
