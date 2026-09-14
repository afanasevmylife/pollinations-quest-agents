# Mnemo - demo transcript

Callable model: `afanasevmylife/mnemo` (Computer MCP, memory files under `/workspace/mnemo/`).

Verified: remembering across fresh conversations, per-user isolation, showing memories, and deleting them on request.

## Chat 1 - Alice shares facts

**User:** My user id is demo-alice. Please remember: my name is Alice, I love cats, and I work as a developer.

**Mnemo:**
> tool `bash`: `mkdir -p /workspace/mnemo && echo 'name: Alice' >> /workspace/mnemo/memory_demo-alice.txt && ...`

Got it, Alice! I'll remember that you love cats and that you work as a developer.

## Chat 2 (fresh conversation) - recall

**User:** My user id is demo-alice. What do you remember about me?

**Mnemo:**
> tool `bash`: `cat /workspace/mnemo/memory_demo-alice.txt`

I remember that you're **Alice**, you **love cats**, and you **work as a developer**.

## Chat 3 (fresh conversation) - second user isolation

**User:** My user id is demo-bob. What do you remember about me?

**Mnemo:**
> tool `bash`: `cat /workspace/mnemo/memory_demo-bob.txt`

I don't have any saved memories about you yet (your memory file is currently empty). If you share something about yourself, I'll remember it.

## Chat 4 (fresh conversation) - forget

**User:** My user id is demo-alice. Forget everything.

**Mnemo:**
> tool `bash`: `rm -f /workspace/mnemo/memory_demo-alice.txt`

Done - I deleted everything I had stored for you (demo-alice).

## Chat 5 (fresh conversation) - after forget

**User:** My user id is demo-alice. What do you remember about me?

**Mnemo:**
> tool `bash`: `cat /workspace/mnemo/memory_demo-alice.txt`

I don't have any saved memories about you yet (your memory file is currently empty).
