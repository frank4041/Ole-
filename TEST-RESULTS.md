# Lagos Life sandbox validation

Tested at desktop 1280×800 and mobile 390×844. JavaScript syntax, production build, WebGL, and standalone-file loading passed.

Mechanics: exactly 3/7 role assignment, team wins, no friendly fire selection, cash pickup, one-use true/fake lures, player lure choice, witness-only anonymous offers, money gates, accepted/rejected silence, visible messes and cleanup, fixture-anchored toilet overflow, physical common-room gathering, distinct random speaking order, real five-second timing, safe typed chat, final vote, tiebreaker, no-ejection ties, one-person gas trap, blocked exits, manual escape and elimination. All five original minigames passed on desktop and mobile.

Visual inspection covered menus, room roofs, wallet HUD, mischief, toilet overflow, anonymous offers, lure choices, street-menu upper/lower sections, case banner, conversation, expanded and lower voting roster, countdown/tiebreaker, result card, and gas alert/escape button at desktop and mobile sizes.

No live deployment, multiplayer or wider Lagos Life integration was tested or performed.

## lagos-tests

```text
desktop PASS: 3/7 roles, cash, real/fake one-use lures, mischief/cleanup, witness-only anonymous bribes, physical meeting, 5s turns, safe group chat, voting, one-person lock, gas escape/death and team wins
mobile PASS: 3/7 roles, cash, real/fake one-use lures, mischief/cleanup, witness-only anonymous bribes, physical meeting, 5s turns, safe group chat, voting, one-person lock, gas escape/death and team wins
JavaScript errors: []
```

## lagos-edge-tests

```text
Actual 5-second speaking turn PASS
One 10-second tiebreaker then no ejection PASS
No-money gates, teammate witness loyalty, player lure choices, anonymous sender masking and menu lower controls PASS
```

## lagos-minigame-tests

```text
desktop production build and all 5 tasks using visible controls PASS
mobile production build and all 5 tasks using visible controls PASS
Five minigames and WebGL passed, no JavaScript errors
```

## lagos-standalone-tests

```text
desktop standalone HTML, WebGL, roles, case banner, chat, tiebreaker and lower roster PASS
mobile standalone HTML, WebGL, roles, case banner, chat, tiebreaker and lower roster PASS
Standalone errors: []
```