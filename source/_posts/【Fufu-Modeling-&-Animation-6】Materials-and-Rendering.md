---
title: 【Fufu Modeling & Animation 6】Materials and Rendering
date: 2026-01-17 12:00:00
categories:
- Model
---

![meeting_01.00_00_02_07.Still002](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_00_02_07.Still002.png)

This project was rendered directly using **Eevee**.

- Eevee is fast, making it ideal for repeated testing of materials and animation  
- It works especially well for cartoon and stylized looks  
- Lighting results are intuitive, so adjustments are quick and efficient  

For a 3D-to-2D (toon) style, physically accurate lighting is not required.  
Because of that, Eevee is a better fit than realistic renderers.

---

### Material Preview

![meeting_01.00_03_51_03.Still054](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_03_51_03.Still054.png)

### Initial Render

![meeting_01.00_04_00_02.Still058](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_04_00_02.Still058.png)

---

## Overall Idea of Toon (3D-to-2D) Materials

The character material is built around **three color layers**:

- Base Color  
- Shadow Color  
- Highlight Color  

The key idea here is that  
**light and shadow are not decided entirely by lighting, but mainly by the material itself.**

This prevents colors from shifting under different lighting conditions,  
keeps the style consistent, and makes the image more stable.

The material node setup is relatively simple.  
ColorRamp or Mix nodes are used to split the shading into clear steps,  
with separate colors assigned for shadows and highlights.

![meeting_01.00_06_49_08.Still073](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_06_49_08.Still073.png)

---

## Background Material

Simply changing the camera background can work,  
but it lacks a gradient.

![meeting_01.00_05_40_07.Still066](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_05_40_07.Still066.png)

![meeting_01.00_05_29_13.Still065](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_05_29_13.Still065.png)

---

### Infinite Background

In animation or camera-movement shots, a common solution is to place a very large plane as the ground and background, then scale or bend it to hide the edges.  
However, once the camera moves or changes angle, edges, seams, or the horizon line often become visible.

The goal of an **infinite background** is not to make the plane bigger,  
but to ensure that **the camera never sees the boundary of the background**,  
while still preserving proper lighting and shadows.

This setup is handled in the **World** shader nodes.

![meeting_01.00_05_49_05.Still001](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_05_49_05.Still001.png)

Adjusting the gradient position:

![meeting_01.00_05_58_09.Still068](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_05_58_09.Still068.png)

---

## Ground Contact and Shadows

At this point, shadows are missing, and the character feels like it is floating.

Adding a visible ground plane breaks the background illusion.

![meeting_01.00_05_59_13.Still069](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_05_59_13.Still069.png)

To solve this, I used a **Shadow Catcher** for the ground.  
The ground itself becomes invisible, but it still receives shadows,  
which prevents the character from looking like it is floating.

![meeting_01.00_06_02_01.Still070](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_06_02_01.Still070.png)

Stylized shadows:

![meeting_01.00_06_49_08.Still073](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_06_49_08.Still073-1769726776227.png)

Final result:

![meeting_01.00_06_47_01.Still072](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%B8%B2%E6%9F%93/meeting_01.00_06_47_01.Still072-1769725840132.png)

---

## Lighting Setup

In a toon-style workflow, lighting is not used to sculpt forms,  
but to **help the material decide light and shadow regions**.

I used a small number of lights (one or two main lights),  
with a 45-degree Rembrandt-style angle on the character.

Since the character has no nose, the effect is subtle.

Two spotlights are used to light the background.

![meeting_01.00_06_23_14.Still071](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_06_23_14.Still071.png)

---

## Camera Movement

The camera work was inspired by dance videos and existing choreography-style shots.

![meeting_01.00_07_55_07.Still077](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_07_55_07.Still077.png)

---

## Musical Staff Animation

The musical staff animation is created by moving UVs with a simple formula in the shader nodes.

![meeting_01.00_06_59_12.Still075](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_06_59_12.Still075.png)

![meeting_01.00_07_16_05.Still076](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_07_16_05.Still076.png)

---

## Final Result

![meeting_01.00_00_02_07.Still002](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB6%E3%80%91%E6%9D%90%E8%B4%A8%E4%B8%8E%E6%B8%B2%E6%9F%93/meeting_01.00_00_02_07.Still002-1769726825568.png)

---

## Conclusion

If I continue refining this model, I will focus on two main directions:

First, further cleaning up the rig and weight structure,  
so the character remains stable during large movements.

The next step is to try importing the model into VR and testing different rig systems.  
If possible, I also hope to turn it into a usable **VRChat character**.