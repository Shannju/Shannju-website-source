---
title: 【Fufu Modeling & Animation 3】Modeling
date: 2026-01-14 12:00:00
categories:
- Model
---

Modeling in Blender is actually quite simple. Let’s go through it step by step.

As the saying goes, “everything starts from a cube.”  
First, press **Shift + A** to add a cube. Then press **Ctrl + 1** to add one level of subdivision, and apply the modifier. This gives us a quad-based sphere.

Adjust the surrounding vertices, and you’ll get a basic head shape.

The head is usually divided into “three sections.” At this stage, we only have the upper and lower parts, so select the middle edge loop and press **Ctrl + B** to bevel it. This creates the basic three-section structure of the head.

![meeting_01.00_00_34_04.Still005](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_00_34_04.Still005.png)

Next, add another level of subdivision and apply it.

![meeting_01.00_00_31_07.Still004](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_00_31_07.Still004.png)

**Small tip: Mirror Modifier**

To make things easier, switch to X-ray mode, select the vertices on the left half and delete them. Then add a **Mirror Modifier** and enable “Show in Edit Mode.”

This way, since the model is symmetrical, you only need to edit one side and the other side will update automatically.

Go back to Object Mode, press **Ctrl + 2** to add two levels of subdivision, and right-click to choose **Shade Smooth**. The head will now look much smoother.

Make some small adjustments to make the shape cuter. At this point, the main head shape is basically done.

I left the eyes for later—they’re the finishing touch, after all. I originally wanted to use textures for facial expressions, but unfortunately I wasn’t able to make that work in the end.

Add the hair.

![meeting_01.00_01_12_14.Still009](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_12_14.Still009.png)

And twin ponytails made with curves!

![meeting_01.00_01_27_14.Still011](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_27_14.Still011.png)

---

## Body

Press **Tab** to enter Edit Mode. Select the middle edge loop and press **Ctrl + B** to bevel it, dividing the body into upper, middle, and lower sections.

![meeting_01.00_01_30_04.Still013](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_30_04.Still013.png)

Adjust the scale and move it slightly upward so the three sections are more evenly spaced.

At the moment the body looks a bit short, so scale it vertically to make it taller.

Then switch to the right view and push it slightly forward to roughly shape the back.

![meeting_01.00_01_31_00.Still014](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_31_00.Still014.png)

Next, add more geometry: press **Ctrl + 1** to add a subdivision and apply it. This gives you more room to edit the shape.

---

### Arms and A-Pose

Now let’s make the arms. Enter Edit Mode and find the four faces where the arms connect to the body. Right-click and choose the “Circle” option under the Loop tools (from the Loop add-on).

![meeting_01.00_01_32_00.Still015](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_32_00.Still015-1769655907074.png)

![meeting_01.00_01_32_10.Still016](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_32_10.Still016.png)

After extruding the arms, adjust the armpit area.

![meeting_01.00_01_34_11.Still018](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_34_11.Still018.png)

Add a **Mirror Modifier** and enable “Clipping / Merge,” which helps prevent issues when editing along the center line.

---

### Legs and Feet

Next, move on to the legs. The process is similar. First, find the faces where the legs connect to the body. Be careful not to use the two faces next to the center line, or the legs may end up fused together.

![meeting_01.00_01_37_07.Still020](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_37_07.Still020.png)

Select the four faces and press **E** to extrude downward, then adjust the shape so the legs naturally hang down.

![meeting_01.00_01_37_13.Still021](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_37_13.Still021.png)

If the extrusion tilts, you can straighten it by scaling to zero along a specific axis.

For the leg shape, keep things simple and round.

Now for the feet: add a loop cut at the ankle using **Ctrl + R**, then press **E** to extrude the foot. Add a few more loop cuts at the bottom to adjust the thickness and shape of the sole. Check the proportions from both the side and the front.

![meeting_01.00_01_40_05.Still022](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_40_05.Still022.png)

Add enough subdivisions to support the shape.

The neck is also very simple: select the faces above the shoulders, press **E** to extrude, then **S** to scale and **G** to move it slightly backward.

![meeting_01.00_01_45_00.Still023](meeting_01.00_01_45_00.Still023.png)

At this point, the body is basically finished.

![meeting_01.00_01_49_09.Still025](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB3%E3%80%91%E5%BB%BA%E6%A8%A1/meeting_01.00_01_49_09.Still025.png)