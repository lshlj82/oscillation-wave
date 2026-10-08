# Oscillations and Waves

This is an interactive, browser-based demo of oscillations and waves. It covers simple harmonic motion, springs and pendulums, damping, traveling and standing waves, the wave equation, resonance, beats, the Doppler effect, and shock waves. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 단순조화운동, 속도와 가속도, 용수철 진동자, 단순조화운동의 에너지, 중력장에서의 용수철 운동, 단진자, 물리진자, 감쇠 진동, 파동의 종류(가로파동과 세로파동), 진행파동, 팽팽한 줄에서 파동의 속력, 파동의 에너지 전달률, 파동방정식, 간섭과 정지파, 공명, 맥놀이, 도플러 효과, 초음속과 충격파를 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `oscillation-wave-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `oscillation-wave-en.html` | American English version |
| `oscillation-wave-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts, and halves are written as (1/2).

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/oscillation-wave-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/oscillation-wave-en.html` or `.../oscillation-wave-ko.html`.

These pages can share a repository with the other demos in the series (`motion-*`, `newton-*`, `energy-*`, `momentum-*`, `rotation-*`, `gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The eighteen sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Simple harmonic motion:** A particle moves on a vertical axis right next to its $x(t)=x_m\cos(\omega t+\phi)$ graph, so its height lines up with the curve. You set the amplitude, frequency and phase constant, and the page reports $T=1/f$, $\omega=2\pi f$, and the current phase.
2. **Velocity and acceleration:** Stacked graphs of $x(t)$, $v(t)=-\omega x_m\sin\omega t$ and $a(t)=-\omega^2x_m\cos\omega t$ share one time cursor, with $v$ and $a$ arrows on the particle. A readout confirms that $a/x=-\omega^2$ at every moment.
3. **Spring oscillator:** A block oscillates on a spring, with the force arrow and the straight line $F=-kx$ underneath. The page gives $\omega=\sqrt{k/m}$, $T=2\pi\sqrt{m/k}$, and checks that $m\omega^2=k$.
4. **Energy in SHM:** $U(t)$, $K(t)$ and their constant sum $\tfrac12 kx_m^2$ are graphed over two periods, with live energy bars.
5. **Spring in gravity:** A mass hangs on a vertical spring. The page marks where the spring ends without the mass and the new equilibrium $x_0=mg/k$, and draws the forces $-k(x+x_0)$ and $mg$. Switching gravity off moves only the equilibrium; the period stays the same.
6. **Simple pendulum:** The pendulum follows the full equation $\ddot\theta=-(g/L)\sin\theta$, next to a dashed pendulum that uses the small-angle formula. You can choose Earth, Moon or Mars gravity. The page compares $T=2\pi\sqrt{L/g}$ with the true period and shows energy bars for $U=mgL(1-\cos\theta)$ and $K$.
7. **Physical pendulum:** A uniform rod or a point mass swings about a pivot. The page graphs $T=2\pi\sqrt{I/mgh}$ against the pivot distance $h$, marks the shortest period at $h=L/\sqrt{12}$ for the rod, and gives the length of the simple pendulum with the same period.
8. **Damped SHM:** A spring, a block and a vane in a liquid, as in the lecture figure. The trace of $x(t)$ stays inside the envelope $x_m e^{-bt/2m}$, and the page gives $\omega'=\sqrt{k/m-b^2/4m^2}$ and compares the simulated energy with $\tfrac12 kx_m^2e^{-bt/m}$.
9. **Kinds of waves:** A transverse wave on a string and a longitudinal wave in a tube of air driven by a piston. One element in each is marked red so you can see that it only oscillates in place.
10. **Traveling waves:** The page draws $y=y_m\sin(kx\mp\omega t+\phi)$ with its wavelength, its crests, and the $t=0$ snapshot, plus the graph of $y(0,t)$. It gives $k=2\pi/\lambda$, $v=\omega/k=\lambda f$, and $y(0,0)=y_m\sin\phi$, and you can reverse the direction of travel.
11. **Wave speed on a string:** A pulse travels along a stretched string. At its peak, the page draws the circle of curvature, the tension $\tau$ on both sides, and the net restoring force from the derivation of $v=\sqrt{\tau/\mu}$.
12. **Energy transport:** String elements are shaded by how fast they move, so you can see the kinetic energy ride along the wave. The page gives $(dK/dt)_\text{avg}=\tfrac14\mu v\omega^2y_m^2$ and $P_\text{avg}=\tfrac12\mu v\omega^2y_m^2$.
13. **Wave equation:** You can choose a sine wave, a pulse, or two pulses. Arrows show the acceleration $\partial^2y/\partial t^2$ of each element, and a movable probe checks that $(\partial^2y/\partial t^2)/(\partial^2y/\partial x^2)=v^2$ for any shape.
14. **Standing waves:** Two traveling waves moving in opposite directions add up to $(2y_m\sin kx)\cos\omega t$. The page marks the nodes at $x=n\lambda/2$ and the antinodes between them.
15. **Resonance:** You can choose a string fixed at both ends, an open tube, or a tube closed at one end. The page draws the standing wave for mode $n$ with its nodes (N) and antinodes (A), gives $\lambda_n=2L/n$ or $4L/(2n-1)$ and the frequency, and can play that frequency as a sound.
16. **Beats:** Two signals $s_1$ and $s_2$ add up to $[2s_m\cos\omega' t]\cos\omega t$, drawn with the slowly varying envelope. The page gives $f_\text{beat}=|f_1-f_2|$, and a sound button lets you hear the beats.
17. **Doppler effect:** A moving source sends out wavefronts toward a moving detector. The page computes $f'=f\frac{v\pm v_D}{v\mp v_S}$, and the detector also counts the wavefronts that actually reach it. The counted ratio agrees with the formula.
18. **Shock waves:** Above the speed of sound, the wavefronts pile up along a Mach cone with $\sin\theta=v/v_S$. The page gives the Mach number, the cone angle, and the source speed in air.

The header animation shows a block oscillating on a spring. A pen on the block draws its motion onto a strip that moves to the right, and the trace becomes a traveling wave. This links the oscillation half of the page to the wave half.

## Notes on the model

- **Animation speed:** Some animations are slowed down so the motion is easy to follow. The pulse in section 11 runs at 1/4 speed, the standing waves in section 15 oscillate slowly, and the Doppler and shock-wave pictures use scaled speeds. The readouts always show the real values, and each slowed picture says so on screen.
- **Numerical integration:** The simple pendulum and the damped oscillator are integrated step by step (fourth-order Runge–Kutta) rather than drawn from a formula. The true period of the pendulum is computed from the complete elliptic integral.
- **Energy readouts:** The pendulum's energy bars are for a mass of 1 kg. The physical pendulum uses the small-angle formula. The damped energy $\tfrac12 kx_m^2e^{-bt/m}$ is an approximation that holds when the damping is light. If $b^2 \ge 4mk$, the page notes that the block no longer oscillates.
- **Sign convention in the Doppler section:** Positive velocities point to the right, from the source S toward the detector D, so the formula is written as $f'=f\frac{v-v_D}{v-v_S}$.
- **Sound:** Sound plays only after you press a button. Resonance plays the real frequency, limited to 20–4000 Hz. Beats plays $f_1+400$ Hz and $f_2+400$ Hz, which moves the tones into an audible range without changing the beat frequency.
- **Display:** The pages follow the system's light or dark setting, and a sun/moon button in the top-right corner switches by hand, and the choice is remembered across pages. Under `prefers-reduced-motion`, the animations start paused and can be played by hand. Only simulations that are currently on screen are animated.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
