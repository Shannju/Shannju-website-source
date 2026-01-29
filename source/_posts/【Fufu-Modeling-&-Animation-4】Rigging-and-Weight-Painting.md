---
title: 【Fufu Modeling & Animation 4】Rigging and Weight Painting
date: 2026-01-16 12:00:00
categories:
- Model
---

Open the character we created earlier—the version **without clothes**.

---

### Quickly Generating a Skeleton with Auto-Rig Pro

First, place the markers (to locate key skeletal points).

![meeting_01.00_01_50_04.Still027](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_01_50_04.Still027.png)

Auto-Rig Pro will then automatically calculate and generate a skeleton based on the model, saving a lot of manual work.

![meeting_01.00_01_51_01.Still028](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_01_51_01.Still028-1769725161009.png)

At this stage, the model is **not yet bound**.  
This step only generates the skeleton structure.

---

### Checking the Skeleton and Generating Controllers (Rig)

![meeting_01.00_01_52_05.Still029](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_01_52_05.Still029.png)

After generating the skeleton, check carefully to make sure there are no obvious issues.

Click **“Match to Controller”**, and Auto-Rig Pro will generate a set of controllers that make the skeleton easier to animate (similar to a rig control system).

Blender’s built-in tools can also generate controllers—the visual style is different, but the underlying principle is the same.

---

### Skin Binding (Bind)

Click the **“Bind”** button.

Switch to **Pose Mode**, move any controller, and you should see the character follow the motion.

![meeting_01.00_02_01_08.Still034](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_02_01_08.Still034.png)

> #### Tips
>
> Sometimes the controllers are “hidden inside” the model and hard to see.  
> Open the Pose panel, and under Viewport Display, enable **“In Front”**.  
> This will make all controllers clearly visible.
>
> You can also enable **X-Axis Mirror** in the top-right corner:
> moving the left wrist will automatically move the right wrist as well.

---

## Hair Not Following the Head: Fix with Constraints

While testing poses, you may notice that the hair (for example, hair made with curves) does not follow the head movement.

![meeting_01.00_01_55_07.Still032](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_01_55_07.Still032.png)

In this case, you need to use **constraints**.

After adding the constraint, go back to Pose Mode and rotate the head controller.  
Now the hair will move together with the head.

---

### Weight Painting

Switch from Object Mode to **Weight Paint Mode**.

Repaint areas where the deformation looks incorrect.

![meeting_01.00_01_58_09.Still033](%E3%80%90Fufu%E5%BB%BA%E6%A8%A1%E4%B8%8E%E5%8A%A8%E7%94%BB4%E3%80%91%E9%AA%A8%E9%AA%BC%E7%BB%91%E5%AE%9A%E4%B8%8E%E6%9D%83%E9%87%8D/meeting_01.00_01_58_09.Still033-1769725257947.png)

> #### Tips: Smooth Tool for Softer Transitions
>
> If the overall weight distribution is mostly fine but a joint transition looks too stiff, use the **Smooth** brush.
> This helps soften the weight transition between two bones.
>
> In many cases, simply using Smooth can fix most weight issues.