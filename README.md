# Pollinations Quest Agents

Test repo for three prompt agents submitted to [pollinations/pollinations](https://github.com/pollinations/pollinations) quests.

## Agents

| Agent | Quest | PR | Callable model |
| --- | --- | --- | --- |
| `mnemo` | [#14821](https://github.com/pollinations/pollinations/issues/14821) - NPC who remembers | [#14886](https://github.com/pollinations/pollinations/pull/14886) | `afanasevmylife/mnemo` |
| `catgpt-comic` | [#14822](https://github.com/pollinations/pollinations/issues/14822) - CatGPT replies with comics | [#14888](https://github.com/pollinations/pollinations/pull/14888) | `afanasevmylife/catgpt-comic` |
| `sirius-elevator` | [#14823](https://github.com/pollinations/pollinations/issues/14823) - Sirius elevator chapter 1 | [#14889](https://github.com/pollinations/pollinations/pull/14889) | `afanasevmylife/sirius-elevator` |

## Layout

- `mnemo/agent.json`, `catgpt-comic/agent.json`, `sirius-elevator/agent.json` - prompt agent configs (same content as the PRs)
- `demos/` - verified transcripts: remembering across fresh chats and user isolation (mnemo), three real comic replies (catgpt-comic), refusal/persuasion/arrival/restart playthrough (sirius-elevator)
