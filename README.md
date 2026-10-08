# Linear Momentum

This is an interactive, browser-based demo of the center of mass, linear momentum and impulse, the conservation of momentum, collisions, and rockets. It comes as two separate pages, one in English and one in Korean.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee (이상훈)**.

> **한국어 요약:** 질량중심, 연속 질량 분포, 입자계의 뉴턴 법칙, 선운동량과 충격량, 운동량 보존, 완전 비탄성 충돌, 탄성 충돌, 2차원 충돌, 로켓을 직접 조작해 볼 수 있는 인터랙티브 웹 데모입니다. 이상훈(Sang Hoon Lee)의 강의 노트를 바탕으로 Claude Opus 5.5가 만들었습니다. 한국어 페이지는 `momentum-ko.html`입니다.

## Files

| File | Description |
| --- | --- |
| `momentum-en.html` | American English version |
| `momentum-ko.html` | Korean version (한국어) |
| `README.md` | This file |

Each page is a single self-contained HTML file with inline CSS and JavaScript. There is no build step and there are no dependencies. The only external request is to Google Fonts for IBM Plex Sans KR. If that request fails, the page falls back to system fonts. Each page links to the other language from its top bar. Equations use real fraction bars, radical signs, and stacked sub- and superscripts, and factors of one half are written as (1/2).

## Running it

Open either file directly in a modern browser, or serve the folder locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/momentum-en.html
```

### Publishing on GitHub Pages

1. Push these files to a repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, then select your branch and the root folder.
3. Visit `https://<user>.github.io/<repo>/momentum-en.html` or `.../momentum-ko.html`.

These pages can share a repository with the other demos in the series (`motion-*`, `newton-*`, `energy-*`, `gauss-*`, `circuits-*`, `rc-*`, `magnetism-*`, `induction-*`, `maxwell-*`). The file names don't collide.

## What's inside

The nine sections follow the order of the lecture notes. Every value is recomputed live as you move the controls.

1. **Center of mass:** Up to eight particles can be placed in the plane. You can drag them, or select one and set its mass and its $x$ and $y$ position with sliders; the center of mass $\vec r_\text{com} = \frac{1}{M}\sum m_i\vec r_i$ follows. A preset with two equal masses puts it exactly at their midpoint.
2. **Continuous mass:** A rod lies between $x_1$ and $x_2$, and you can make one end heavier. The page computes $x_\text{com} = \frac{1}{M}\int x\,dm$ numerically and compares it with the uniform-rod result $\frac{1}{2}(x_1+x_2)$.
3. **Newton's second law for a system:** A shell explodes into two fragments at the top of its flight. While both fragments are in the air, their center of mass stays on the original parabola. The page reports the distance between the two, which stays at zero.
4. **Momentum and impulse:** A ball bounces off a wall. A plot of the force $F(t)$ shows that its area is $J = \Delta p = 2mv$, and a dashed curve shows that a contact five times longer gives the same impulse with a much smaller force.
5. **Conservation of momentum:** Two carts collide through a spring bumper whose bounciness you can adjust. Live graphs show $p_1$ and $p_2$ changing while $P$ stays flat, and the kinetic energy dipping during contact.
6. **Completely inelastic collisions:** The colliding bodies stick together. On a number line, $v' = v_\text{com}$ divides $v_1$–$v_2$ in the ratio $m_2 : m_1$, and the page checks the energy loss against $\Delta K = -\frac{m_1m_2(v_1-v_2)^2}{2(m_1+m_2)}$.
7. **Elastic collisions in 1D:** The page shows the formulas for $v_1'$ and $v_2'$, checks that both $P$ and $K$ are conserved, and shows that the relative velocity reverses. Presets cover equal masses, $m_1 \gg m_2$, and a wall.
8. **Collisions in 2D:** In an elastic collision at an adjustable impact parameter, the page draws the momentum vector triangle $\vec p_{1i} = \vec p_{1f} + \vec p_{2f}$. It also gives the angle between the outgoing paths, which is 90° for equal masses.
9. **Rockets:** A rocket burns its fuel. The page shows the thrust $T = Rv_\text{rel}$, the changing mass and acceleration, and $\Delta v = v_\text{rel}\ln(M_i/M)$ on a graph.

## Notes on the model

- **Section 3:** The explosion is set by a relative speed between the fragments. Momentum conservation fixes each fragment's velocity.
- **Section 5:** The bumper is a spring with a damper, tuned to match the chosen bounciness. At zero bounciness, the carts stick together.
- **Timing:** Some animations are slowed down so the motion is easy to follow, but every readout shows the real value.
- **Display:** The page follows your system's light or dark setting, and a sun/moon button in the top-right corner switches by hand, and the choice is remembered across pages. If you have `prefers-reduced-motion` turned on, the animation at the top of the page stays still.

## Credits

- Lecture notes: Sang Hoon Lee (이상훈)
- Demo design and code: Claude Opus 5.5

## License

No license has been chosen yet. Before publishing, add a `LICENSE` file if you want others to be able to reuse the code. Also confirm with the author of the lecture notes how their material may be shared.
