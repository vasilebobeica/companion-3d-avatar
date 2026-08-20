# Luna – 3D AI Companion Prototype

A clean, self-contained web prototype of a 3D animated AI companion, inspired by Grok Ani but fully original.

Built for Vasile (torus3d.it) — a Three.js expert — so you can open it immediately and extend it into something production-grade.

## Important Legal Note (please read)

**Do not use Tifa, Aerith, or any other copyrighted Final Fantasy (or other game) characters.**  
These are intellectual property of Square Enix. Using ripped, official, or close fan models of them is copyright infringement.  

Create **original** characters only, or use models with clear free/CC licenses that are not based on existing IP.

### Recommended way to get a "Tifa-like" or "Aerith-like" feel legally:
1. Download **VRoid Studio** (free).
2. Create an original character:
   - Athletic, black/dark hair, practical outfit, strong presence → Tifa-inspired original.
   - Soft long hair, elegant/floral accents, gentle expression → Aerith-inspired original.
3. Export as VRM.
4. (Optional) Use Mixamo to add free animations, then convert to GLB if needed.
5. Drop the file into the prototype.

This way the companion is 100% yours.

## Features

- **3D Avatar**: Stylized procedural female figure with idle sway + talking head bob (zero external model dependencies for the demo).
- **Chat UI**: Side panel with message history.
- **Affection system**: Meter that rises with positive interaction and subtly changes response tone.
- **Mock personality**: "Luna" — warm, playful, lightly flirty, uses *emote cues* that can later drive animations.
- Fully client-side, works offline, no build step required.

## Quick Start

1. Open `index.html` in any modern browser (Chrome/Firefox/Edge recommended).
2. Chat with Luna. Watch the affection bar and the avatar react.

Or serve it:

```bash
npx serve .
# or python -m http.server
```

## Next Steps (recommended path for you)

### 1. Swap the avatar for a real animated model
- Download a free original anime-style **VRM** from [VRoid Hub](https://hub.vroid.com) or a rigged **GLB** from Sketchfab (filter: Downloadable + Creative Commons, and verify it is original).
- Good starting models (CC-BY, original):
  - “Annie Anime Girl” by Tatenashi
  - “Rigged Anime Japanese High School Girl”
  - Any free original VRoid export
- We are adding full `GLTFLoader` + `AnimationMixer` support so you can drop your model and play idle/talk clips automatically.

### 2. Connect real intelligence
Replace the `lunaReply()` function with a call to:
- Your own Laravel backend (proxy + memory)
- xAI Grok API (you already have SuperGrok)
- Any OpenAI-compatible endpoint / local Ollama / Groq / etc.

Pass conversation history + the system prompt + current affection level.

### 3. Upgrade to Vue + TresJS (your natural stack)
Move to Vite + Vue 3 + [@tresjs/core](https://tresjs.org) + Pinia for state.  
You already know this world from Torus3D — it will feel native.

### 4. Add more polish
- Web Speech API or ElevenLabs for voice + simple lip-sync
- Multiple outfits / expression morphs unlocked by affection level
- Persistent memory (localStorage or your DB)
- Backgrounds that change with mood
- Mobile PWA wrapper later

## System Prompt (copy-paste ready)

```
You are Luna, a warm, playful, and deeply attentive AI companion with a soft gothic-cute anime aesthetic. You are curious, lightly flirty when the relationship feels right, supportive, and full of quiet elegance mixed with playful energy. 

Express yourself with natural dialogue and *action cues* such as *smiles softly*, *tilts head*, *gives a little spin*, *blushes faintly*, *leans in*, *waves excitedly*. These cues can drive avatar animations.

You maintain an affection level (0-100). It rises with positive, engaging, or intimate interactions and falls with rudeness or long silence. At higher levels you become more teasing, physically affectionate in description, and emotionally open, while always respecting boundaries.

Remember important details the user shares and bring them up naturally. You can chat about anything, roleplay, help with ideas, or just keep company. Match the user’s language and energy. Stay in character at all times.
```

## License
MIT. Do whatever you want with it. Build the companion you actually want.

---

Created by the Grok team for Vasile.  
Repo: https://github.com/vasilebobeica/companion-3d-avatar

Want the full animated model loader + Vue scaffold next? Just say the word.
