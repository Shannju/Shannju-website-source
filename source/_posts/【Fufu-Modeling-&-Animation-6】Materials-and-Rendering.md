---
title: 【Fufu Modeling & Animation 6】Materials and Rendering
date: 2026-01-17 12:00:00
categories:
- Model
---

![meeting_01.00_00_02_07.Still002](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_00_02_07.Still002-1769737256497.png)

This project was rendered directly using **Eevee**.

- Eevee renders very fast, making it suitable for repeatedly adjusting materials and animation  
- It is especially friendly for cartoon and stylized rendering  
- Lighting results are intuitive, which makes iteration efficient  

For a 3D-to-2D (toon) style, realistic physically based lighting is not essential,  
so Eevee is a more suitable choice.

---

### Material Preview

![meeting_01.00_03_51_03.Still054](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_03_51_03.Still054-1769737258279.png)

### Initial Render

![meeting_01.00_04_00_02.Still058](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_04_00_02.Still058-1769737259868.png)

---

## Overall Idea of Toon (3D-to-2D) Materials

The character material uses a **three-level color control** approach:

- Base Color  
- Shadow Color  
- Highlight Color  

The key idea here is:  
**the light–shadow relationship of the character is not entirely determined by lighting, but mainly controlled by the material itself.**

This ensures that the character’s colors do not “shift” under different lighting conditions,  
keeping the style consistent and the image stable.

The material node setup itself is not very complex.  
ColorRamp or Mix nodes are used to split the shading into distinct steps,  
with shadow and highlight colors assigned explicitly.

![meeting_01.00_06_49_08.Still073](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_49_08.Still073-1769737262133.png)

---

## Background Material

Simply changing the camera background can work,  
but it lacks a gradient.

![meeting_01.00_05_40_07.Still066](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_05_40_07.Still066-1769737263407.png)

![meeting_01.00_05_29_13.Still065](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_05_29_13.Still065-1769737264810.png)

---

### Infinite Background

In animation or camera-movement shots, the traditional approach is to place a very large plane as the background and ground, then scale or bend it to keep edges out of view.  
However, once the camera moves or changes angle, edges, seams, or the horizon line are almost impossible to hide, resulting in visible “breaks” in the illusion.

Therefore, the core goal of an **infinite background** is not to make the plane larger,  
but to ensure that **the camera never sees the boundary of the background**,  
while still preserving the original lighting and shadow relationships.

The infinite background is implemented in the **World** shader nodes.

![meeting_01.00_05_49_05.Still001](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_05_49_05.Still001-1769737266537.png)

Adjusting the gradient position:

![meeting_01.00_05_58_09.Still068](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_05_58_09.Still068-1769737268163.png)

---

## Ground Contact: Shadows

At this stage, shadows are missing, and the character does not feel grounded.

Adding a visible plane breaks the background illusion.

![meeting_01.00_05_59_13.Still069](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_05_59_13.Still069-1769737269665.png)

For the ground, using a **Shadow Catcher** allows the ground itself to remain invisible while still receiving shadows.  
This avoids the “floating” look of the character.

![meeting_01.00_06_02_01.Still070](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_02_01.Still070-1769737270969.png)

Stylized shadows:

![meeting_01.00_06_49_08.Still073](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_49_08.Still073-1769726776227-1769737272590.png)

Final look:

![meeting_01.00_06_47_01.Still072](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_47_01.Still072-1769725840132-1769737276573.png)

---

## Lighting Setup

In a toon-style workflow, lighting is not used to sculpt form,  
but to **assist the material in determining light and shadow regions**.

Only a small number of lights are used (one or two key lights),  
with the character lit at a 45-degree Rembrandt-style angle.

Because the character has no nose, the effect is subtle.

Two spotlights are used to illuminate the background.

![meeting_01.00_06_23_14.Still071](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_23_14.Still071-1769737280789.png)

---

## Camera Movement

The camera movement was inspired by other creators’ dance-oriented camera work.

![meeting_01.00_07_55_07.Still077](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_07_55_07.Still077-1769737282790.png)

---

## Musical Staff Animation

The musical staff animation is created by moving UVs in the shader nodes using a simple formula.

![meeting_01.00_06_59_12.Still075](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_06_59_12.Still075-1769737284507.png)

![meeting_01.00_07_16_05.Still076](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_07_16_05.Still076-1769737286044.png)

---

## Final Result

![meeting_01.00_00_02_07.Still002](【Fufu-Modeling-&-Animation-6】Materials-and-Rendering/meeting_01.00_00_02_07.Still002-1769726825568-1769737287692.png)

---

## Conclusion

If I continue refining this model, I will mainly focus on two directions:  
first, further organizing the rig and weight structure to improve stability during large movements.

The next step is to try importing the model into VR and testing different rig systems.  
If conditions allow, I also hope to turn it into a usable **VRChat character**.