---
title: 【Fufu Modeling & Animation 5】Clothing
date: 2026-01-16 15:00:00
categories:
- Model
---

### Two Common Ways to Make Clothes

There are generally two approaches to making clothes for a character: **cloth simulation**, or **using meshes with weights**.

Cloth simulation can look very realistic, but it is demanding on performance, time-consuming to tweak, and not very beginner-friendly.  
So here I chose the more stable and versatile method: **mesh + weights**.

The biggest advantage of this method is that clothes are easy to control and modify. It also makes it very convenient to change outfits later.

---

### Copying the Body Mesh and Inheriting Weights

Before starting, make sure you open a character that has already been properly rigged and weighted.

As long as the body is correctly bound, when you copy part of the body mesh to create clothing, the **vertex weights will be copied as well**.  
In other words, the clothes “inherit” the body’s weights from the very beginning.

This single step helps avoid many common problems later—such as broken weights, strange deformations, or clipping—and is the most critical part of the entire workflow.

---

### Top

To make the top, simply select the area of the body mesh where the clothing should be.

![meeting_01.00_02_04_05.Still035](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_04_05.Still035.png)

Use a loop-based selection to select the entire clothing area at once.  
Once you have a clean “clothing shape” selection, duplicate it and separate it from the body. This gives you an independent clothing mesh.

Enter Edit Mode for the clothing, select all, and scale slightly along the normal direction to push the clothes outward.  
This helps avoid surface intersection and shading artifacts caused by overlapping with the body.

![meeting_01.00_02_04_13.Still036](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_04_13.Still036.png)

If you want the clothes to have thickness, you can add a **Solidify Modifier**.

![meeting_01.00_02_05_05.Still037](meeting_01.00_02_05_05.Still037.png)

From here, you can start adding clothing details and shaping the design.

![meeting_01.00_02_08_13.Still039](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_08_13.Still039.png)

---

## Skirt and Pants

Pants (or skirts) are made in almost the same way as the top.

![meeting_01.00_02_27_12.Still044](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_27_12.Still044.png)

Sleeves follow the same logic.

![meeting_01.00_02_30_05.Still046](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_30_05.Still046.png)

Add some bevels to soften the edges.

![meeting_01.00_02_48_12.Still049](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_48_12.Still049.png)

Shoes are also modeled using the same principles.

![meeting_01.00_02_31_07.Still047](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_31_07.Still047.png)

---

### Small Accessories and Constraints

Small accessories on clothing—such as buttons or zipper pulls—can be made by copying small meshes directly from the clothing.

If you don’t want these details to deform noticeably during animation, you can use **constraints** to control them.

Here, I made a tie.

![meeting_01.00_02_13_03.Still040](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB5%E3%80%91%E8%A1%A3%E6%9C%8D/meeting_01.00_02_13_03.Still040.png)

![meeting_01.00_02_16_01.Still042](C:%5CUsers%5Cshan%5COneDrive%20-%20Goldsmiths%20College%5C%E6%A1%8C%E9%9D%A2%5C%E5%BB%BA%E6%A8%A1%5Cmeeting_01.00_02_16_01.Still042.png)

---

### Final Result

![meeting_01.00_03_34_05.Still053](C:%5CUsers%5Cshan%5COneDrive%20-%20Goldsmiths%20College%5C%E6%A1%8C%E9%9D%A2%5C%E5%BB%BA%E6%A8%A1%5Cmeeting_01.00_03_34_05.Still053.png)

The biggest advantage of this mesh-copy-with-weights method is how much time and effort it saves.

Because the clothes start with the same weights as the body, they follow the character naturally when you pose it, with very few issues.  
For beginners, this means less frustration with weight painting and far fewer clipping problems.

Since each piece of clothing is an independent mesh, you can also use collections to quickly switch between different outfits.  
This makes the method especially suitable for outfit changes and multiple design variations.