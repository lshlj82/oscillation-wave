# Interactive Physics Demos

Interactive, bilingual (English / 한국어) web pages for introductory mechanics and waves. Each page pairs the explanation from the lecture notes with live simulations: move a slider and every number, graph and animation on the page is recomputed on the spot.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

## Pages

| Topic | English | 한국어 | Sections |
| --- | --- | --- | --- |
| Work and energy | [energy-en.html](energy-en.html) | [energy-ko.html](energy-ko.html) | 11 |
| Rotational motion | [rotation-en.html](rotation-en.html) | [rotation-ko.html](rotation-ko.html) | 12 |
| Oscillations and waves | [oscillation-wave-en.html](oscillation-wave-en.html) | [oscillation-wave-ko.html](oscillation-wave-ko.html) | 18 |

Every page has a language switch in the top bar that links to its counterpart.

### Work and energy
Work by a constant force · variable forces · kinetic energy · work done by gravity · work done by a spring · power · conservative forces · conservation of mechanical energy · a frictionless track · reading a potential energy curve U(x) · friction and thermal energy.

### Rotational motion
Rotational kinematics · linear and angular variables · rotational inertia · common shapes · the parallel-axis theorem · torque · τ = Iα · work and rotational kinetic energy · rolling · rolling down a slope · angular momentum and its conservation · gyroscope precession.

### Oscillations and waves
Simple harmonic motion · velocity and acceleration · the spring oscillator · energy in SHM · a spring in a gravitational field · the simple pendulum · the physical pendulum · damped SHM · kinds of waves · traveling waves · wave speed on a string · energy transport · the wave equation · standing waves · resonance in strings and tubes · beats · the Doppler effect · shock waves.

## Using the pages

Each page is a single self-contained HTML file. There is nothing to install or build:

- **Locally:** download or clone the repository and open any `.html` file in a browser.
- **Online with GitHub Pages:** in the repository go to **Settings → Pages**, choose **Deploy from a branch**, select the branch (e.g. `main`) and the root folder, and save. The pages are then available at
  `https://<your-username>.github.io/<repository-name>/energy-en.html` and so on.

Every simulation has its own controls. Animated ones have **Play/Pause** and **Start again** buttons, and a few sections in *Oscillations and waves* (resonance, beats) have a **Play sound** button that plays the actual frequency through the Web Audio API.

## How they are built

- Plain HTML, CSS and JavaScript in one file per page: no frameworks, no build step, no external scripts.
- Drawings and graphs are inline SVG, redrawn every animation frame. Only simulations currently on screen are animated.
- Motion is computed from the physics, not keyframed: the pendulum integrates the full equation with sin θ (RK4), the damped oscillator integrates m ẍ + b ẋ + kx = 0, and the Doppler detector counts the wavefronts that actually reach it.
- Text lives in an `I18N` object at the top of each page's script; the English and Korean files share the same markup and simulation code.
- The only network resource is the **IBM Plex Sans KR** web font from Google Fonts, with system-font fallbacks, so the pages also work offline.

## Accessibility and display

- Follows the system **light/dark** setting.
- Respects **prefers-reduced-motion**: animations start paused and can be played by hand.
- Responsive layout down to phone width; keyboard focus is visible on all controls.
- Sound plays only after a button press.

## 한국어 안내

강의 노트의 설명과 인터랙티브 시뮬레이션을 함께 담은 역학·파동 웹 페이지입니다. 조절 막대를 움직이면 화면의 모든 값, 그래프, 애니메이션이 바로 다시 계산됩니다.

- **주제:** 일과 에너지, 회전운동, 진동과 파동 (각각 영어판 `-en.html`, 한국어판 `-ko.html`)
- **사용법:** 각 페이지는 HTML 파일 하나로 되어 있어 설치가 필요 없습니다. 파일을 브라우저로 열거나, GitHub Pages(**Settings → Pages**)로 배포하면 됩니다.
- **제작:** <b>이상훈(Sang Hoon Lee)</b>의 강의 노트를 바탕으로 <b>Claude Opus 5.5</b>가 만들었습니다.
