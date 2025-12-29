---
title: AI and 3D Modeling
date: 2025-12-01 00:00:12
categories:
- Model
---

  

# AI与建模 | AI and 3D Modeling

在2025年学习建模，不可避免的问题就是AI。如果我将这次完全只做传统建模，未免有些浪费。我花时间在这方面做了思考，并且和ChatGPT讨论了这个问题，以下是一些心得。
Learning 3D modeling in 2025 inevitably involves addressing AI. It would be a waste of opportunity to focus solely on traditional modeling. I have spent time reflecting on this and discussed the topic with ChatGPT; here are some of my insights.

我个人的判断是，当下的3D建模AI还停留在软表面+贴图生成，对于硬表面建模辅助有限。这可以类比图片生成的模型：LLM接触的都是渲染后的效果图，自然不能生成渲染前的建模文件。
My personal assessment is that current 3D modeling AI is still limited to soft-surface and texture generation, providing limited assistance for hard-surface modeling. This is analogous to image generation models: LLMs are trained on rendered final images, so they naturally cannot generate the underlying modeling source files.

---

> **我 (Me):** 对于传统3D建模，AI 可以在什么方向补充？
> For traditional 3D modeling, in what areas can AI provide support?
>
> **GPT:** AI 可以在 **不改变传统 3D 建模本质（建模师的结构判断 + 审美 + 拆解能力）** 的前提下，成为强大的“增能工具”。 它主要补在 **繁琐、重复、低产出、流程阻塞** 的部分，而不取代创作性。
> AI can serve as a powerful "enhancer" without changing the essence of traditional 3D modeling (the modeler's structural judgment, aesthetics, and deconstruction skills). It mainly addresses **tedious, repetitive, low-output, and workflow-bottleneck** stages, rather than replacing creativity.

---

### ⭐ AI 在传统 3D 建模里的 8 个关键方向
### 8 Key Directions for AI in Traditional 3D Modeling

#### **1. 参考图生成 / 设计辅助 | Reference Generation & Design Assistance**

AI 可以帮你解决：缺少合适的设计参考；寻找素材耗时。
AI helps solve: lack of design references and time-consuming asset searches.

* **Stable Diffusion / Midjourney** → 快速出风格、材质、构型 (Quickly generate styles, materials, and forms)
* **生成 turn-around** (Generate multi-view/turn-around references)
* **生成贴图参考** (Generate texture references like skin, fabric, or metal wear)

🔹 **对建模师最大帮助：找参考从 2 小时 → 10 分钟。**
🔹 **Biggest Benefit:** Reducing reference hunting from 2 hours to 10 minutes.

> **心得：** 这主要适合设计阶段，从预制展示交流的高保真渲染到美术概念的三视图，使用图片生成的功能就可以完成想法的沟通。AI生成的三视图能不能用？存疑。
> **Insight:** This is mainly suitable for the design phase. From high-fidelity renders for communication to conceptual orthographic views, image generation can facilitate idea sharing. However, whether AI-generated orthographic views are truly usable remains questionable.

---

#### **2. 阴影图 / 轮廓图 / 分解图生成 | Shadow, Silhouette & Exploded View Generation**

AI 可以将复杂的参考图自动转换：
AI can automatically transform complex reference images:

* **轮廓 (Silhouettes)** → 清晰边界，用于蓝图建模 (Clear boundaries for blueprint modeling)
* **色块 (Color Blocks)** → 区域拆分，便于拓扑规划 (Area segmentation for topology planning)
* **高光/阴影提取 (Highlight/Shadow Extraction)** → 结构定位 (Structural positioning)
* **多视角推断** (Multi-view inference to improve modeling accuracy)

🔹 **对建模师最大帮助：快速读懂参考结构，减少试错。**
🔹 **Biggest Benefit:** Quickly understanding reference structures and reducing trial and error.

> **心得：** 如上文，我认为这更属于 CV（计算机视觉）处理的范围，有了 LLM，让没机会用 CV 的人也可以接触到。
> **Insight:** As mentioned above, I believe this falls more under Computer Vision (CV) processing. LLMs allow those who wouldn't normally use CV tools to access these capabilities.

---

#### **3. AI 驱动的自动拓扑 / 重拓扑 | AI-Driven Auto-Retopology**

现在已有 AI 重拓扑工具：
Existing AI retopology tools:

* **ZBrush ZRemesher** (内置智能拓扑 / Built-in smart topology)
* **Blender + Quad Remesher**
* **instant-meshes + AI 辅助** (AI-assisted instant-meshes)
* **AutoTopo、AIQuad** (正在变成插件的研究原型 / Research prototypes becoming plugins)

🔹 **最大帮助：从半天的手动 retopo → 10 分钟自动草稿，然后建模师再精修即可。**
🔹 **Biggest Benefit:** From half a day of manual retopology to a 10-minute auto-draft, which the modeler then refines.

> **心得：** 这次使用 Blender 的 SmartUV，没想到已经带了 AI 重拓扑。说实话这个很惊讶到。
> **Insight:** I used Blender's SmartUV this time and was surprised to find it already incorporates AI retopology. Honestly, it was quite impressive.

---

#### **4. 智能 UV 展开 | Smart UV Unwrapping**

AI 可以学习最佳切线方式，避免：
AI learns optimal seam placement to avoid:
* **拉伸 (Stretching)**
* **重叠 (Overlapping)**
* **不合理拼接 (Illogical seams)**

例如：**RizomUV** 的智能算法，以及 **Blender Smart UV Project** 正在加入的学习数据。
Examples include RizomUV's smart algorithms and Blender's Smart UV Project, which is integrating learning data.

🔹 **价值：UV 从痛苦的手工 → 半自动化。**
🔹 **Value:** Turning the painful manual UV process into a semi-automated one.

---

#### **5. 贴图生成 / 材质辅助 | Texture Generation & Material Assistance**

AI 在纹理方面成熟度很高：
AI maturity in texturing/materials is very high:

* **Adobe Substance AI Generator / ArmorPaint AI / AI PBR pack generator**
* **自动生成 (Auto-generate):** BaseColor, Normal, Roughness, Metallic, Height, AO.
* **纹理缝合、统一色调** (Texture stitching and tone unification)

🔹 **价值：让建模师不用自己画所有贴图 → 专注细节美术。**
🔹 **Value:** Allowing modelers to focus on artistic detail rather than painting every texture from scratch.

---

#### **6. 3D 扫描 → AI 清理/补全 | 3D Scan Cleanup & Completion**

适合场景资产、布料、自然元素、角色基础模型：
Suitable for environment assets, fabric, natural elements, and base character models:

* **去噪、修洞、补面** (Denoising, hole filling, and surface patching)
* **快速规整拓扑** (Rapid topology regularization)
* **Gaussian Splatting 系列** (AI 3D 重建 / AI 3D reconstruction)

🔹 **价值：降低做真实道具/自然场景的成本。**
🔹 **Value:** Lowering the cost of creating realistic props and natural scenes.

> **心得：** 这个我觉得可以应用到像素风格渲染上。先建立简单的 3D 草模，再经过像素渲染器，既可以保留精细的效果，又可以去掉其 3D 边缘，从而达到风格化的效果。
> **Insight:** I think this can be applied to pixel-art rendering. By creating simple 3D blockouts and passing them through a pixel renderer, one can retain detailed effects while removing 3D edges to achieve a stylized look.

---

#### **7. Prompt → 粗模 | Prompt to Blockout**

注意：**AI 只能生成“草模/块体”，不适合直接用在项目**。
Note: AI is currently only suitable for "blockouts/whiteboxes" and not for direct project use.

* **代表工具 (Tools):** OpenAI Shap-E, 3DTopia, Tripo, Luma “Genie”.
* **用途:** 作为 Blockout、灵感快试、早期关卡填充。
* **Use Cases:** Blockouts, rapid inspiration testing, early-stage level filling.

🔹 **价值：自动生成基础模型，建模师负责清修与细化。**
🔹 **Value:** Automated base models; the modeler is responsible for cleanup and detailing.

---

#### **8. AI 动态 LOD / 优化 | AI Dynamic LOD & Optimization**

用于游戏或 VR 场景：
Used for gaming or VR scenarios:

* **自动生成 LOD1/LOD2/LOD3** (Auto-generation of LODs)
* **自动烘焙贴图** (Auto-baking maps: normal, ambient occlusion)
* **多边形数优化与自动合批** (Polygon count optimization and auto-batching)

🔹 **价值：将原本枯燥、易出错且配置敏感的流程自动化。**
🔹 **Value:** Automating processes that were previously tedious, error-prone, and configuration-sensitive.