---
title: 【Fufu Modeling & Animation 4】Rigging and Weight Painting
date: 2026-01-16 12:00:00
categories:
- Model
---

Open the character we created earlier — the version **without clothing**.

---

### Quickly Generating a Skeleton with Auto-Rig Pro

Place the markers (to define key skeletal points).

![meeting_01.00_01_50_04.Still027](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_01_50_04.Still027-1769737211759.png)

Auto-Rig Pro will automatically calculate and generate a skeleton based on the model, which saves a lot of manual work.

![meeting_01.00_01_51_01.Still028](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_01_51_01.Still028-1769725161009-1769737213312.png)

At this stage, the model is **not actually bound yet**.  
This step only generates the corresponding skeleton.

---

### Checking the Skeleton and Generating Controllers (Rig)

![meeting_01.00_01_52_05.Still029](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_01_52_05.Still029-1769737214780.png)

After the skeleton is generated, first check whether anything looks incorrect.

Click **“Match to Rig”**, and Auto-Rig Pro will generate a set of controllers that make the skeleton easier to manipulate (similar to a rig control system).  
Blender’s built-in tools can also generate controllers. The appearance is different, but the principle is essentially the same.

---

### Skin Binding (Bind)

Click the **Bind** button.

Switch to **Pose Mode**, move any controller, and you should see the character follow the movement.

![meeting_01.00_02_01_08.Still034](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_02_01_08.Still034-1769737216526.png)

> #### Tips
>
> Sometimes the controllers are “hidden inside” the model and hard to see.  
> Open the Pose panel, and under Viewport Display, enable **In Front**.  
> This makes all controllers clearly visible.
>
> You can also enable **X-Axis Mirror** in the top-right corner:  
> when you move the left wrist, the right wrist will move at the same time.

---

## Hair Not Following the Head: Solving It with Constraints

While testing poses, you may notice that the hair (for example, hair made with curves) does not follow the head movement.

![meeting_01.00_01_55_07.Still032](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_01_55_07.Still032-1769737219654.png)

In this case, you need to use a **constraint**.

After setting up the constraint, go back to Pose Mode and rotate the head controller.  
The hair will now move together with the head.

---

### Weight Painting

Switch from Object Mode to **Weight Paint Mode**.

Repaint the areas where the deformation looks incorrect.

![meeting_01.00_01_58_09.Still033](【Fufu-Modeling-&-Animation-4】Rigging-and-Weight-Painting/meeting_01.00_01_58_09.Still033-1769725257947-1769737221161.png)

> #### Tips: Smooth Tool for Softer Transitions
>
> If the overall weights are mostly fine but a joint transition looks too stiff, use the **Smooth** brush.  
> This helps soften the weight transition between two bones.
>
> In many cases, Smooth alone can fix most weight-related issues.
