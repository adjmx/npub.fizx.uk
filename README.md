# npub.fizx.uk

> Nostr profile viewer — search an npub, see profile + recent notes.

**Live**: <https://npub.fizx.uk>

## Stack

- [Vite](https://vitejs.dev/) + React 18 + TypeScript
- Tailwind CSS
- [nostr-tools](https://github.com/nbd-wtf/nostr-tools)
- lucide-react

## Nostr

- **Login**: NIP-07 (browser extension) + NIP-55 (Amber callback URI)
- `kind:0` — profile metadata
- `kind:1` — short notes

Reads from `wss://relay.fizx.uk`.

## Develop

```bash
npm install
npm run dev
```

## Build + deploy

```bash
npm run build
rsync -avz --delete -e "ssh -p 2121" dist/ root@88.218.206.187:/var/www/npub.fizx.uk/
```

VPS: `88.218.206.187`. Full server / nginx / SSL / DNS notes for the wider deployment live in the local `code_vibe/CLAUDE.md` (not pushed; this README is the public-facing summary).

---

_Sister repo on the other side: <https://github.com/macos-node/npub.upleb.uk>_
