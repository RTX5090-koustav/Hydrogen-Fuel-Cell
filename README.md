# H₂ / SPORT — prototype 01

A self-contained, interactive hydrogen-combustion V8 hybrid concept in a procedural 2020 Range Rover Sport-inspired body. Built from the original Hydrogen-Fuel-Cell project's scene concept, warm colour direction, five palettes, orbit controls, labels and animated energy flow. The V-shaped fuel-cell chemistry has deliberately been replaced with combustion and hybrid energy flow following the updated brief.

## Open it

Extract the ZIP and open `index.html` in a current browser with WebGL. No installation or build is required. Three.js is included locally; the app does not require a CDN or online fonts. `ls460.html` forwards old links to the new entry point.

For local development, run `python -m http.server 8000` from this folder and visit `http://localhost:8000`.

## Try the prototype

1. Select **Run demo** for electric launch, V8 handover, engine charging and regenerative braking. The demo runs about 28 seconds of active-tab simulation time.
2. Or select **Start system**, then raise **Accelerator**. Default handover is 2,500 RPM, adjustable from 1,500 to 4,000 RPM.
3. Raise **Brake / regeneration** to decelerate. Braking overrides accelerator input. At rest or with a full battery, regeneration stops.
4. Turn engine charging on or off. It charges only while the V8 is running and battery state is below 80%.
5. Explore **Exterior**, **Cutaway**, **Powertrain**, or **V8 view**. Drag to orbit and scroll/pinch to zoom. Focus the canvas and use arrow keys and +/- for keyboard camera control.
6. **Reset drive** restores the energy stores and clears pedals. **Reset view** restores the camera. Palette preference is stored locally when storage is available.

## What is simulated

- Battery → integrated motor → transmission/transfer case → both axles at launch.
- Hydrogen tank → combustion V8 → mechanical AWD after the selected RPM, with a smooth torque blend.
- V8 generator charging uses additional hydrogen. Regeneration recovers only part of braking energy; friction brakes supply the remainder.
- Illustrative 2,500 kg mass, 12 kWh battery, 6 kg H₂ tank, 140 kW motor, 300 kW V8, 18 kW generator, and 70 kW maximum mechanical regeneration input (72% stored).
- One effective transmission ratio, no gear shifts, simplified drag and traction limit. Real hybrids use more complex control than a single RPM handover.
- Low battery permits engine launch. Empty hydrogen permits remaining electric drive. Both depleted prevents propulsion.
- All gauges are model outputs, not telemetry, real conversion performance or factory specifications. Piston animation is deliberately slowed.
- Hydrogen combustion can produce NOx. This is not a zero-emissions claim.

The vehicle is a recognisable procedural styling prototype, not an exact manufacturer CAD replica. Interior, doors opening, road driving, detailed thermal control and validated component packaging are not included in this first version.

## Source layout

| File | Purpose |
| --- | --- |
| `index.html` | Accessible page structure and learning content |
| `styles.css` | Responsive interface and original warm palette direction |
| `scene.js` | Procedural vehicle, V8, drivetrain, camera and particle paths |
| `simulation.js` | Pure hybrid state and energy model; assumptions in CONFIG |
| `app.js` | Controls, demo, UI updates and animation loop |
| `simulation.test.js` | Deterministic behavioural checks; run with `node simulation.test.js` |
| `vendor/` | Three.js r128 and its MIT licence |
| `reference/ls460-original.html` | Unmodified original source for comparison (uses original CDN links) |

## Publish to GitHub Pages

1. Create a **new repository** for this prototype to keep the original project untouched.
2. Upload the contents of this folder so `index.html`, the JavaScript files, `styles.css`, `.nojekyll` and `vendor/` are at the repository root. Do not upload only the ZIP or nest the app inside another folder.
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Choose **main** and **/(root)**, then **Save**.
6. Wait for GitHub's Pages deployment to finish. Open the URL displayed in Pages settings and try the demo.

All app paths are relative, so repository subpaths work. No secrets, build service, API key or backend is needed. No changes have been pushed to the original repository.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## References and attribution

- Original: https://github.com/RTX5090-koustav/Hydrogen-Fuel-Cell — RTX5090-koustav; Unlicense. The original licence is retained in `LICENSE`.
- Original live page: https://rtx5090-koustav.github.io/Hydrogen-Fuel-Cell/ls460.html
- 2020 vehicle styling: https://www.landrover.co.uk/content/dam/lrdx/pdfs/uk/brochures/range-rover-sport/Range-Rover-Sport-Brochure-1L4941920000BGBEN01P_tcm295-663803.pdf
- Hybrid inspiration, not control replication: https://www.audi.com/en/press-releases/lamborghini-revuelto-the-first-super-sports-v12-hybrid-hpev-15298
- Three.js: https://threejs.org/ — MIT; see `vendor/THREE-LICENSE.txt`.

Independent educational prototype; not affiliated with Land Rover, Ferrari or Lamborghini.
