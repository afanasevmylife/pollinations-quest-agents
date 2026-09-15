# Pollinations Quest Agents

Test repo for three prompt agents submitted to [pollinations/pollinations](https://github.com/pollinations/pollinations) quests.

## Agents

| Agent | Quest | PR | Callable model |
| --- | --- | --- | --- |
| `mnemo` | [#14821](https://github.com/pollinations/pollinations/issues/14821) - NPC who remembers | [#14886](https://github.com/pollinations/pollinations/pull/14886) | `afanasevmylife/mnemo` |
| `catgpt-comic` | [#14822](https://github.com/pollinations/pollinations/issues/14822) - CatGPT replies with comics | [#14888](https://github.com/pollinations/pollinations/pull/14888) | `afanasevmylife/catgpt-comic` |
| `sirius-elevator` | [#14823](https://github.com/pollinations/pollinations/issues/14823) - Sirius elevator chapter 1 | [#14889](https://github.com/pollinations/pollinations/pull/14889) | `afanasevmylife/sirius-elevator` |

## Try them

```bash
curl https://gen.pollinations.ai/v1/chat/completions \
  -H "Authorization: Bearer $POLLINATIONS_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "afanasevmylife/sirius-elevator",
    "messages": [{"role": "user", "content": "Take me to floor 1."}]
  }'
```

Swap the model for `afanasevmylife/mnemo` or `afanasevmylife/catgpt-comic`. Get a key at [enter.pollinations.ai](https://enter.pollinations.ai/keys); calls use the caller's Pollen. Note: identical request bodies may return cached responses - vary the wording when re-testing.

## Layout

- `mnemo/`, `catgpt-comic/`, `sirius-elevator/` - `agent.json` + README per agent (same content as the PRs)
- `demos/` - verified transcripts: remembering across fresh chats and user isolation (mnemo), three real comic replies (catgpt-comic), refusal/persuasion/arrival/restart playthrough (sirius-elevator)
- `findings.md` - alpha feedback from building and testing these agents (Computer MCP persistence, response caching)
