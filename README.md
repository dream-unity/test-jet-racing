# Vector Apex

**Dream Unity fighter-jet relational racing**

[Play the live GitHub Pages build](https://dream-unity.github.io/test-jet-racing/)

Vector Apex is a browser-native 3D aerospace racing game in which relational inference determines the racing line. The player observes formations and transformations, commits by flying into a candidate corridor, then separately receives cognitive-choice and flight-execution outcomes.

## Core game

- Accessible arcade fighter-jet flight with pitch, yaw, roll, throttle, drag, braking, stability assistance and afterburner.
- Third-person chase camera, procedural course scenery, gates, boost effects and AI competitors.
- Desktop keyboard/mouse, gamepad and multitouch controls.
- Relational Grand Prix, Training, Transfer Trial, Assessment and Pure Flight modes.
- Procedural seeded challenges with machine-checked unique solutions and diagnostic distractors.
- Separate relational and motor telemetry, local records and session export.
- Static, backend-free GitHub Pages deployment with vendored Three.js.

## Relational challenge engine

The logical layer is independent from rendering and represents entities, attributes, relations, premises, transformations, candidates and solver results before projecting them into flight geometry. Challenge families include:

- vector chains;
- dynamic analogies;
- reference-frame shifts;
- rule stacking;
- topology routing;
- trajectory prediction;
- temporal transformations;
- multi-constraint corridors;
- structural classification;
- higher-order relations.

Incorrect gates are generated from plausible error models such as inversion, subject/object reversal, wrong frame selection, partial transformation and single-constraint violations. Challenge metadata is deterministic under a supplied seed where practical.

## Controls

### Desktop

- **WASD / arrow keys:** steer
- **Q / E:** roll
- **Shift:** afterburner
- **Space:** air brake
- **Escape:** pause
- **Mouse / gamepad:** supported by the in-game input layer

### Touch

Use the multitouch flight stick, throttle rail, boost, brake and pause controls displayed during a race.

## Run locally

The project has no build step and no backend requirement. Serve the repository root over HTTP:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080` in a WebGL-capable browser.

## Validation

```bash
npm test
```

The test command runs the relational challenge stress suite, browser-safety checks and static project validation. The Pages workflow additionally validates repository-subpath asset paths before deployment.

## Architecture

- `src/main.js` — application and race-state orchestration
- `src/flightPhysics.js` — arcade flight model
- `src/relationalEngine.js` — relational representation, generation and solving
- `src/challengeSystem.js` — in-course challenge lifecycle and commitments
- `src/course.js` — racecourse and sector construction
- `src/aiRacers.js` — opponent trajectories and race position
- `src/adaptiveDifficulty.js` — multidimensional performance adaptation
- `src/telemetry.js` — cognitive/motor scoring and persistence
- `src/rendering/` — Three.js world, jet and environmental presentation
- `src/input.js` — keyboard, mouse, gamepad and multitouch input
- `src/ui.js` — HUD, menus, overlays and post-race reporting
- `tests/` — deterministic challenge and project-integrity validation

Performance data remains local to the browser unless the player explicitly exports a session file. The in-game relational model is not presented as a clinically validated IQ measure.
