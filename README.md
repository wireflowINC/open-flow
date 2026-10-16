# Open Flow

Make an 18 second launch film for your product from 8 clips and a headline.
Open source, rendered in the cloud.

[![The Open Flow launch film. Click to watch it with sound.](assets/open-flow-film.gif)](https://cdn.wireflow.ai/videos/remotion/22491/wo4mecwh84.mp4)

This film came out of the command below with no options. [Watch it with sound](https://cdn.wireflow.ai/videos/remotion/22491/wo4mecwh84.mp4) (1920x1080, 18 seconds).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

## Make yours in 3 steps

You need Node 20 or newer. Nothing to install.

**1. Get your free API key.**

- Sign up free at [wireflow.ai](https://www.wireflow.ai/?utm_source=github&utm_medium=readme&utm_campaign=open-flow) and finish the short welcome steps (the key page opens after that).
- Go to the [API keys page](https://www.wireflow.ai/settings?tab=api-keys&section=api-keys&utm_source=github&utm_medium=readme&utm_campaign=open-flow) and make a key.
- Tick `workflows:write` and `workflows:execute`. Read access is already ticked.

**2. Get the code.**

```bash
git clone https://github.com/wireflowINC/open-flow
cd open-flow
export WIREFLOW_API_KEY="wf_live_..."
```

**3. Render your film.**

```bash
npm run film -- --brand "Acme" --headline "Launch day. Every version." --cta "acme.com" --clips ./my-clips
```

In 2 to 4 minutes it prints a link to your MP4 and a link to the board it
made in your Wireflow account. The render costs 0 credits. Run `npm run film`
with no options first if you want to see the demo film come out.

## Swap the clips, headline and CTA

| Option | What it changes | Limit |
| --- | --- | --- |
| `--clips ./my-clips` | The video clips. A folder, or a comma list of files or links. | 8 clips |
| `--headline "..."` | The closing line over the moving cards. | 45 characters |
| `--brand "..."` | The big name on the end card. | 24 characters |
| `--cta "..."` | The button on the end card, like your site. | 30 characters |
| `--music song.mp3` | The soundtrack. Default is the Open Flow score. | mp3, wav, m4a |
| `--no-render` | Build the board but do not render. | |

Tips for clips:

- Name them in the order you want (`1.mp4`, `2.mp4`, ...). Clip 1 is on
  screen the longest. Clip 4 is the "your product" shot.
- Give fewer than 8 and they repeat to fill the slots.
- Tall phone clips look best, since the cards are tall. Wide clips get cropped.
- 3 to 15 seconds each is plenty. mp4, mov, m4v or webm, up to 100MB each.

Want to change one thing later? Open the board link, edit a Text node or drop
a new clip into an Import node, then press Run on the film node.

## How it works

1. [`WireflowFilm.tsx`](WireflowFilm.tsx) is the film, a Remotion composition. Every clip and line of text is a prop.
2. Wireflow hosts a built copy of it as a Block, with each prop as an input port.
3. [`film.mjs`](film.mjs) uploads your clips and makes a board: one node per clip, a music node and three text nodes, all wired into one Video Editor node.
4. It runs that node, and Wireflow renders the film in the cloud at 1920x1080, 30 fps, with sound.
5. You get the MP4, plus a board you can edit and run again.

More detail, and how to render on your own machine with Remotion, is in
[DETAILS.md](DETAILS.md).

## Make films from Claude

Prefer to just ask? Add Wireflow to Claude and say "make an Open Flow launch
film with these clips and the headline Ship it." Claude builds the board,
shows you frames, and renders it.

- Claude (web or desktop): [add the Wireflow connector](https://www.wireflow.ai/mcp?utm_source=github&utm_medium=readme&utm_campaign=open-flow)
- Claude Code: install the [Wireflow skill](https://github.com/wireflowINC/wireflow-skill)

## What is free

The film renders at 0 credits on a free Wireflow account. Paid AI shots
(video models, AI actors, voice) use credits, and the board tells you the
cost before anything is charged.

## License

MIT, see [LICENSE](./LICENSE). The two fonts in `fonts/` are under the SIL
Open Font License (notices in that folder). The demo clips are Wireflow
marketing footage and are not covered by the MIT license; use your own clips
for your film.

## Want us to make your launch video?

We make launch films, ads and shorts for startups.
[Get a free media plan](https://www.wireflow.ai/startups?utm_source=github&utm_medium=readme&utm_campaign=open-flow).
