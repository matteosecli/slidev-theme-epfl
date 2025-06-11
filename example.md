---
theme: ./  # Use the theme in the current directory
layout: cover
title: "An EPFL Theme for Slidev"
# image: './theme/backgrounds/epfl-aerial-view-2.jpg'
# image-light: './theme/backgrounds/epfl-aerial-view-2.jpg'
# image-dark: './theme/backgrounds/epfl-rlc-night-view-1.jpg'
author: "Matteo Seclì"
affiliation: "LTPN"
# date: "Jun 11, 2025"
header: "Some Conference | 10–13 Jun 2025 | Lausanne"
footer: "Your Name"
number: true
transition: slide-up
---

<!-- No need to put anything here -->

---
transition: slide-up
---

## Outline

- 🎨 Custom colors and fonts
- 🏷️ EPFL branding
- 🚀 Responsive layouts
- 👨‍💻 Code highlighting

---
layout: section
color: --epfl-rouge
image: '/theme/backgrounds/epfl-pedestrians.jpg'
transition: slide-up
---

## Intro

Some introductory stuff you may want to say

---
transition: fade
---

## EPFL Theme Colors

The EPFL Slidev theme defines a rich palette of formal and casual colors for your presentations.

Go to the next slides for details.

---
transition: fade
---

## Formal Colors (1/2)

| Name            | Variable              | Example                                 |
|-----------------|----------------------|-----------------------------------------|
| Swiss Red       | `--epfl-swiss-red`   | <span style="color:#ff0000;">&#9608;&#9608;&#9608;</span> <code>#ff0000</code> |
| Rouge           | `--epfl-rouge`       | <span style="color:#e30613;">&#9608;&#9608;&#9608;</span> <code>#e30613</code> |
| Groseille       | `--epfl-groseille`   | <span style="color:#b51f1f;">&#9608;&#9608;&#9608;</span> <code>#b51f1f</code> |
| Léman           | `--epfl-leman`       | <span style="color:#00a79f;">&#9608;&#9608;&#9608;</span> <code>#00a79f</code> |
| Canard          | `--epfl-canard`      | <span style="color:#007480;">&#9608;&#9608;&#9608;</span> <code>#007480</code> |

---
transition: fade
---

## Formal Colors (2/2)

| Name            | Variable              | Example                                 |
|-----------------|----------------------|-----------------------------------------|
| Taupe           | `--epfl-taupe`       | <span style="color:#413d3a;">&#9608;&#9608;&#9608;</span> <code>#413d3a</code> |
| Perle           | `--epfl-perle`       | <span style="color:#cac7c7;">&#9608;&#9608;&#9608;</span> <code>#cac7c7</code> |

---
transition: fade
---

## Casual Colors (1/2)

| Name         | Variable                | Example                                 |
|--------------|------------------------|-----------------------------------------|
| Mont Rose    | `--epfl-mont-rose`     | <span style="color:#f39869;">&#9608;&#9608;&#9608;</span> <code>#f39869</code> |
| Vert d’Eau   | `--epfl-vert-eau`      | <span style="color:#c2ddb0;">&#9608;&#9608;&#9608;</span> <code>#c2ddb0</code> |
| Rose         | `--epfl-rose`          | <span style="color:#ed6e9c;">&#9608;&#9608;&#9608;</span> <code>#ed6e9c</code> |
| Acier        | `--epfl-acier`         | <span style="color:#4f8fcc;">&#9608;&#9608;&#9608;</span> <code>#4f8fcc</code> |
| Soufre       | `--epfl-soufre`        | <span style="color:#fbee66;">&#9608;&#9608;&#9608;</span> <code>#fbee66</code> |


---
transition: fade
---

## Casual Colors (2/2)

| Name         | Variable                | Example                                 |
|--------------|------------------------|-----------------------------------------|
| Carotte      | `--epfl-carotte`       | <span style="color:#ec6608;">&#9608;&#9608;&#9608;</span> <code>#ec6608</code> |
| Zinzolin     | `--epfl-zinzolin`      | <span style="color:#5c2483;">&#9608;&#9608;&#9608;</span> <code>#5c2483</code> |
| Chartreuse   | `--epfl-chartreuse`    | <span style="color:#c8d300;">&#9608;&#9608;&#9608;</span> <code>#c8d300</code> |
| Marron       | `--epfl-marron`        | <span style="color:#5b3428;">&#9608;&#9608;&#9608;</span> <code>#5b3428</code> |
| Ardoise      | `--epfl-ardoise`       | <span style="color:#453a4c;">&#9608;&#9608;&#9608;</span> <code>#453a4c</code> |

---
transition: slide-up
---

## How to Use

You can use these colors in your slides by referencing the CSS variable, for example:

```css
color: var(--epfl-rouge);
background-color: var(--epfl-leman);
```

Or in markdown frontmatter:

```yaml
color: --epfl-canard
```

---
layout: section
color: --epfl-leman
image: '/theme/backgrounds/epfl-cleanroom.jpg'
transition: slide-up
---

## Your Results

If you have any

---
transition: fade
---

## State of the Art

You can write $\LaTeX$ equations:

$$
\begin{align}
\nabla \cdot \vec{D} &= \rho \\
\nabla \cdot \vec{B} &= 0 \\
\nabla \times \vec{E} &= -\frac{\partial \vec{B}}{\partial t} \\
\nabla \times \vec{H} &= \frac{\partial \vec{D}}{\partial t} + \vec{J}
\end{align}
$$

---
transition: slide-up
---

## More Equations

You may want to explain your qubits:

$$
\hat{H} = E_C \left( \frac{1}{2} - n_g \right) \sigma_z + \frac{E_J}{2} \sigma_x
$$

And say more stuff afterwards

---
layout: section
color: --epfl-canard
image: '/theme/backgrounds/epfl-cleanroom.jpg'
transition: slide-up
---

## Conclusions & Outlook

---
transition: slide-up
---

## Conclusions

You can uncover bullet points with the `epfl-fade-clicks` class (try to click to uncover).

```markdown
<v-clicks class="epfl-fade-clicks">

- Conclusion One
- Conclusion Two
- Conclusion Three

</v-clicks>
```

<div class="h-[1rem]"/>

<v-clicks class="epfl-fade-clicks">

- Conclusion One
- Conclusion Two
- Conclusion Three

</v-clicks>

---
layout: image
class: bg-cover bg-center bg-no-repeat
style: "background-image: url('/theme/backgrounds/epfl-logo-statue.jpg')"
---

<!-- No nned to put anything here -->

---
layout: section
color: --epfl-taupe
image: '/theme/backgrounds/epfl-blackboard.jpg'
transition: slide-up
---

## Backup slides

---
transition: slide-up
---

## Some backup stuff

You may want to have some backup material.
