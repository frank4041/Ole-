# Who Be Thief? — Lagos Life test sandbox

A solo, browser-based social-deduction prototype: one human, nine simulated bots, three hidden thieves and seven crew. This is a test build for mechanics intended for Lagos Life; it is not yet connected to a separate Lagos Life game or live multiplayer service. All naira is fictional game currency.

## Play / build

Download the standalone HTML and open it in a modern WebGL-enabled browser, or run `npm ci` then `npm run dev` and open the displayed local address. `npm run build` produces the static `dist/` deployment. `vercel.json` is included; no live deployment was performed for this update.

## Core rules

- Exactly three random thieves and seven crew among ten actors. No police, no role selector, no friendly-fire elimination between thieves.
- Crew win by completing five machine tasks or ejecting all three thieves. Thieves win at living thief/crew parity or if the round timer expires. Ejecting one thief does not end the round.
- Five stages retain the existing machine minigames. Tap a yellow-marked machine to approach and interact. Use / E appears only in range.
- Roofs cover rooms you are not inside; characters, bodies, reports and witnesses obey room and line-of-sight checks.

## Common-room palaver

Reports or emergency meetings gather all surviving characters in the common room immediately, preserving their prior positions for return after voting. A random, nonrepeating order gives each survivor five seconds to make a case. The active-speaker banner says “Make your case if you no be thief” and highlights your turn. Typed group chat remains available throughout; bots contribute simulated testimony and discussion. A final 30-second vote follows the speaking turns. A tied top vote receives one 10-second tiebreaker; still tied means no ejection. No player vote counts as skip.

Bots use direct witness testimony, misdirection, accepted bribes, and limited support for an accusation you make in chat. This is rule-based simulated conversation, not live human chat, voice chat, or server-connected AI. The round clock is paused during meetings and menus.

## Cash and street moves

Walk over green money bundles to collect ₦50 / ₦100; bots can collect them too. Every actor starts each round with ₦300. Wallets, messes and offers reset each round. Open **Lagos** for street actions:

- **Money call:** everyone gets one lure per round. Real puts down ₦100 from the caller’s wallet; fake promises money without depositing it. Nearby bots may approach. A player receiving a call can take their chances or ignore it. The caller’s truthfulness is not revealed by the offer UI.
- **Anonymous bribe:** a thief can offer ₦100 to an actual crew witness of their elimination. The recipient sees no sender identity. A bot may accept silence or take the money and refuse; a human can accept/reject and still freely chat or vote. This does not erase existing observations.
- **Pee:** leaves a visible puddle that slows anyone crossing it.
- **Graffiti:** leaves persistent red wall tags.
- **Litter:** leaves visible rubbish.
- **Clog toilet:** only in Washroom; dirt fills a toilet bowl, water overflows around the fixture, movement slows in the spill, and the round loses eight seconds.
- **Clean this room:** clears messes and earns ₦50.
- **Lock one person + gas:** thief-only; exactly one other living person must be in the room, and they must be crew. The thief relocates just outside and the exits seal. Only one trap can be active. The eight-game-second countdown ends in a non-graphic elimination unless the target breaks the lock. A player presses **Escape gas** five times; bots have a simulated escape chance. Entrances and exits are blocked for other actors too. Meetings release the trap. Trap cooldown: 45 seconds; other mischief: 12 seconds.

## Controls

Tap open ground, or WASD/arrows to walk. Tap machines, or E to use. R report; K eliminate (thief); Q lights (thief); G map; M emergency meeting after 10 seconds, once per round; P/Escape pause. Touch buttons include **Lagos**, contextual **Use**, and **Escape gas** during a trap. Keyboard focus and reduced-motion preferences are respected.

## Scope and handoff

The economy is in-memory virtual cash, with no real-money payments. There is no online multiplayer, account authentication, persistent economy, real voice conversation, or synchronization yet. The email entry option remains an unverified, session-only profile. Thief selection is intentionally hidden; retrying starts a new random draw.

Gameplay and rendering are in `game.js`, with the Lagos functions grouped after the base renderer: `initLagos`, `lagosTick`, `renderLagos`, `beginMeeting`, `meetingTick`, `lure`, `bribe`, `evilAction`, and `lockRoom`. Adapting these to the wider Lagos Life game will require that game’s player, world, wallet, networking and meeting systems.

## Backups and assets

`backups/pre-lagos/` preserves the machine-interaction version before this expansion. Earlier user-upload and working-source backups are retained. Preserve `licenses/` and `assets/manifest.json`: selected Kenney Space Station Kit models are CC0; the Biomes cargo model is MIT. Procedural room, toilet, cash, mess and trap geometry is original.

`TEST-RESULTS.md` records desktop/mobile verification. Test scripts require Playwright; it is not a runtime or deployment dependency.
