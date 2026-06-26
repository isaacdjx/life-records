# 全类型图片生成 Prompt 指南

本文档为项目中所有数据类型的图片生成提供统一的 Prompt 规范、模板和示例。
所有图片统一采用真实摄影风格，对标《国家地理》杂志品质。

---

## 通用规范（适用于所有类型）

| 项目 | 规范 |
|------|------|
| 分辨率 | 1792×1024px（7:4 宽幅） |
| 格式 | WebP |
| 风格 | 真实摄影（Photorealistic），国家地理杂志品质 |
| 光线 | 优先选择黄金时刻（Golden Hour）、蓝调时刻（Blue Hour）或戏剧性自然光 |
| 构图 | 广角镜头，展示全景的建立性镜头 |
| 主体 | 以风景/自然/建筑为主，不以人物为主体 |
| 禁忌 | 无文字、无水印、无人工元素 |
| 色彩 | 高动态范围，色彩丰富但自然 |

### 通用 Prompt 后缀

所有 Prompt 末尾应附加以下标准化后缀：

```
National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

---

## 1. 雪山图鉴（Mountains）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `mountains_global.json` |
| 存储目录 | `data/mountain_images/` |
| 命名规则 | `{id}.webp`，如 `1.webp`（珠穆朗玛峰） |

### 视觉风格

高清真实摄影风格的风光大片。山峰主体占画面 40%~60%，留出天空和前景层次感。
侧光突出山体立体感，雪线清晰，冰川纹理可见，岩壁和积雪对比分明。
冷暖对比色调——山体冰蓝冷色调，天空或光线带暖色。壮观、敬畏、宁静的自然感。

### Prompt 模板

```
Photorealistic landscape photograph of [山名英文], [海拔]m, [所在地区], majestic snow-capped peak with visible glaciers and ice ridges, golden hour dramatic side lighting, layered composition with [前景元素] in foreground, crisp detail on snow and rock textures, deep blue sky with wispy clouds, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 按类型调整前景和氛围

| 类型 | 前景元素 | 氛围关键词 |
|------|----------|------------|
| 极高峰（8000m+） | 冰碛、乱石坡、远方云海 | `extreme altitude, thin atmosphere, wind-blown snow plumes, deep blue sky` |
| 高峰（7000m+） | 冰川末端、冰塔林 | `massive glaciers, seracs, dramatic cloud formations` |
| 著名雪山 | 湖泊倒影、森林、草甸 | `iconic silhouette, mirror lake reflection, alpine meadows` |
| 火山雪峰 | 樱花/热带植被、城市远景 | `volcanic cone, symmetrical shape, cultural landscape foreground` |
| 禁登神山 | 寺庙、经幡、晨雾 | `sacred untouched peak, mystical clouds, prayer flags, morning mist` |

### 按地区调整环境

| 地区 | 环境特征 |
|------|----------|
| 喜马拉雅 | 褐色山谷、经幡、蓝天极深、高海拔稀薄感 |
| 横断山脉/云南 | 森林植被丰富、云海翻涌、峡谷纵深 |
| 天山/昆仑 | 干燥荒漠前景、戈壁与雪山对比 |
| 阿尔卑斯 | 绿色牧场、木屋、针叶林、湖泊 |
| 安第斯 | 干旱高原、仙人掌、盐湖 |
| 非洲 | 稀树草原、热带云层 |
| 日本 | 樱花/红叶、五重塔、湖泊 |
| 北美/阿拉斯加 | 冰川入海、针叶林、野生动物 |

### 示例 Prompt

#### 珠穆朗玛峰（id=1, 极高峰, 8849m）
```
Photorealistic landscape photograph of Mount Everest, 8849m, Himalayas Nepal-Tibet border, towering snow-capped pyramid peak with wind-blown snow plumes at summit, massive Khumbu glacier and icefall visible, golden hour dramatic side lighting from the west, layered composition with rocky moraine and prayer flags in foreground, deep indigo sky at extreme altitude, thin atmosphere haze, crisp detail on ice ridges and rock bands, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 乔戈里峰 K2（id=2, 极高峰, 8611m）
```
Photorealistic landscape photograph of K2 Mount Godwin-Austen, 8611m, Karakoram Pakistan-China border, savage steep pyramid peak with dramatic snow and ice flutings, Baltoro glacier winding below, golden hour side lighting casting deep shadows on the north face, layered composition with ice seracs and glacial moraine in foreground, extreme altitude deep blue sky, wind-blown snow banner at summit, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 梅里雪山（id=42, 禁登神山, 6740m）
```
Photorealistic landscape photograph of Meili Snow Mountain Kawagebo Peak, 6740m, Yunnan China, sacred unclimbed peak emerging from dramatic swirling clouds, golden morning light illuminating the snow-covered summit while lower slopes remain in shadow, Tibetan prayer flags and Feilai Temple in foreground, mystical atmosphere with cloud sea in Mekong valley below, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 富士山（id=91, 火山雪峰, 3776m）
```
Photorealistic landscape photograph of Mount Fuji, 3776m, Japan, perfectly symmetrical volcanic cone with snow-capped summit, golden hour warm light, layered composition with Chureito Pagoda and cherry blossoms in foreground, Lake Kawaguchi mirror reflection, soft pink and orange sky gradients, iconic Japanese landscape, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 马特洪峰（id=78, 著名雪山, 4478m）
```
Photorealistic landscape photograph of the Matterhorn, 4478m, Swiss Alps Zermatt, iconic pyramidal peak with sharp ridges and snow-covered faces, blue hour twilight with alpenglow on summit, perfect reflection in Riffelsee alpine lake in foreground, surrounding Alpine peaks and glaciers, crisp mountain air atmosphere, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | id | 名称 | 海拔 | 类型 |
|--------|-----|------|------|------|
| 1 | 1 | 珠穆朗玛峰 | 8849m | 极高峰 |
| 2 | 2 | 乔戈里峰 K2 | 8611m | 极高峰 |
| 3 | 30 | 贡嘎山 | 7556m | 高峰 |
| 4 | 42 | 梅里雪山 | 6740m | 禁登神山 |
| 5 | 91 | 富士山 | 3776m | 火山雪峰 |
| 6 | 78 | 马特洪峰 | 4478m | 著名雪山 |
| 7 | 19 | 南迦巴瓦峰 | 7782m | 高峰 |
| 8 | 50 | 玉龙雪山 | 5596m | 著名雪山 |
| 9 | 85 | 乞力马扎罗山 | 5895m | 著名雪山 |
| 10 | 76 | 勃朗峰 | 4809m | 著名雪山 |

---

## 2. 国家公园（National Parks）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `parks_global.json` |
| 存储目录 | `data/park_images/` |
| 命名规则 | `{id}.webp` |

### 视觉风格

广袤的风光摄影，捕捉每个公园最具标志性的自然特征。优先选择黄金时刻或蓝调时刻拍摄，
展现公园的代表性地貌——无论是峡谷、瀑布、草原、雨林还是火山。
画面应传达自然的壮阔与原始之美，色调鲜明但自然，注重大气透视和层次感。

### Prompt 模板

```
Photorealistic landscape photograph of [公园名英文], [国家]. [标志性特征描述]. Dramatic natural lighting at [golden hour/blue hour/sunrise/sunset], wide-angle lens capturing the sweeping scale, rich natural colors, sharp detail throughout. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 按地貌类型调整

| 地貌类型 | 关键元素 | 氛围关键词 |
|----------|----------|------------|
| 峡谷/地质 | 岩层纹理、深切河谷、层叠色彩 | `layered rock formations, deep canyon, geological wonder, warm desert light` |
| 热带雨林 | 密林、瀑布、云雾 | `lush tropical canopy, misty atmosphere, waterfalls, verdant green` |
| 草原/稀树草原 | 广阔地平线、野生动物剪影 | `endless golden grassland, dramatic sky, wildlife silhouettes, African sunset` |
| 火山/地热 | 蒸汽、彩色温泉、火山口 | `geothermal steam, vivid mineral colors, volcanic landscape, otherworldly` |
| 高山/冰川 | 雪峰、冰碛湖、U型谷 | `alpine grandeur, glacial lakes, snow-capped peaks, pristine wilderness` |
| 海岸/海洋 | 悬崖、海蚀柱、碧海 | `dramatic coastal cliffs, turquoise waters, sea stacks, ocean spray` |
| 喀斯特/石林 | 石柱、溶洞、翠绿植被 | `karst pillars, misty valleys, lush vegetation, ethereal atmosphere` |
| 沙漠 | 沙丘、星空、干裂盐湖 | `sculpted sand dunes, stark beauty, extreme contrast, vast emptiness` |

### 示例 Prompt

#### 黄石国家公园（Yellowstone, 美国）— 大棱镜温泉
```
Photorealistic landscape photograph of Grand Prismatic Spring, Yellowstone National Park, USA. Massive hot spring with vivid rainbow-colored mineral rings radiating outward — deep blue center surrounded by yellow, orange, and rust-red bacterial mats. Steam rising dramatically against dark pine forest backdrop. Aerial-angle perspective showing the full prismatic pattern. Golden hour side lighting enhancing the brilliant colors. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 张家界国家森林公园（Zhangjiajie, 中国）— 石柱云海
```
Photorealistic landscape photograph of Zhangjiajie National Forest Park, China. Towering quartzite sandstone pillar mountains rising dramatically from a sea of white mist, lush green vegetation clinging to vertical cliff faces, multiple stone pillars receding into the distance creating incredible depth. Soft morning light filtering through the mist, ethereal and mystical atmosphere. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 百内国家公园（Torres del Paine, 智利）— 三塔日出
```
Photorealistic landscape photograph of Torres del Paine National Park, Chile. The iconic three granite towers illuminated by first light of sunrise, glowing fiery orange-red against a deep blue pre-dawn sky. Turquoise glacial lake in foreground reflecting the towers, Patagonian steppe grassland in mid-ground. Dramatic cloud formations swirling around the peaks. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 塞伦盖蒂国家公园（Serengeti, 坦桑尼亚）— 角马大迁徙
```
Photorealistic landscape photograph of Serengeti National Park, Tanzania. Vast golden savanna stretching to the horizon with thousands of wildebeest migrating across the plains, dust clouds rising from the herd. Dramatic African sunset sky with deep orange and purple clouds. Scattered acacia trees silhouetted against the sky. Immense sense of scale and natural spectacle. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 十六湖国家公园（Plitvice, 克罗地亚）— 翡翠瀑布群
```
Photorealistic landscape photograph of Plitvice Lakes National Park, Croatia. Cascading series of turquoise and emerald lakes connected by countless waterfalls flowing over travertine barriers, surrounded by dense ancient beech and fir forest. Autumn foliage in golden and russet tones contrasting with the vivid blue-green water. Soft diffused light creating a fairy-tale atmosphere. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | 名称 | 国家 | 标志性特征 |
|--------|------|------|------------|
| 1 | 黄石国家公园 | 美国 | 大棱镜温泉 |
| 2 | 张家界国家森林公园 | 中国 | 石柱云海 |
| 3 | 百内国家公园 | 智利 | 三塔日出 |
| 4 | 塞伦盖蒂国家公园 | 坦桑尼亚 | 角马大迁徙 |
| 5 | 大峡谷国家公园 | 美国 | 分层岩壁 |
| 6 | 九寨沟国家公园 | 中国 | 五花海 |
| 7 | 班夫国家公园 | 加拿大 | 路易斯湖 |
| 8 | 十六湖国家公园 | 克罗地亚 | 翡翠瀑布群 |
| 9 | 伊瓜苏国家公园 | 巴西/阿根廷 | 魔鬼咽喉瀑布 |
| 10 | 纳米布-诺克卢夫特国家公园 | 纳米比亚 | 死亡谷枯树沙丘 |

---

## 3. 暗夜星空（Dark Sky）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `darksky_global.json` |
| 存储目录 | `data/darksky_images/` |
| 命名规则 | `{id}.webp` |

### 视觉风格

专业天文摄影风格，展现银河拱桥横跨地面景观的壮丽夜景。
长曝光捕捉繁星密布的天空，星云和银河核心清晰可见。
地面景观提供前景锚定——可以是沙漠、山脉、天文台、湖泊或标志性建筑。
色调以深蓝、紫色和银白色为主，地面可带微暖色（月光或远方灯光）。

### Prompt 模板

```
Stunning astrophotography of [地点名英文], [国家]. [地面景观特征] under a brilliant Milky Way arc stretching across the entire sky. Long exposure night photography, countless stars, deep space nebulae visible, galactic core bright and detailed. [前景/氛围描述]. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 按观测环境调整

| 环境类型 | 前景元素 | 氛围关键词 |
|----------|----------|------------|
| 沙漠/干旱地带 | 沙丘、岩石拱门、干裂地面 | `bone-dry desert air, zero light pollution, infinite visibility, warm sand tones` |
| 高原/高山 | 雪山剪影、高山湖泊、稀薄大气 | `high altitude clarity, thin atmosphere, brilliant star density, alpine silhouette` |
| 天文台 | 望远镜圆顶、观测设施 | `observatory domes, scientific frontier, rotating star trails around dome` |
| 海岛/海岸 | 岩石海岸线、灯塔、海面倒影 | `ocean reflecting starlight, coastal rocks, light house beam, sea mist` |
| 森林/草地 | 树木剪影、空地、野花草甸 | `dark forest silhouette, clearing in woods, fireflies, natural frame` |
| 古迹/文化景观 | 废墟、石阵、古建筑 | `ancient ruins under eternal stars, timeless connection, stone circle` |

### 示例 Prompt

#### 阿塔卡马沙漠（Atacama, 智利）— ALMA 望远镜与银河
```
Stunning astrophotography of Atacama Desert, Chile. The ALMA radio telescope array — dozens of white parabolic dishes arranged on the Chajnantor Plateau at 5000m altitude — under a breathtaking Milky Way arc. The galactic core blazing with millions of stars, Magellanic Clouds visible near the horizon. Bone-dry desert air providing extraordinary clarity, every star pinpoint sharp. Faint airglow bands in green and red. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 纳米布兰德自然保护区（NamibRand, 纳米比亚）— 枯树星空
```
Stunning astrophotography of NamibRand Nature Reserve, Namibia. Ancient dead camel thorn trees — twisted white trunks and bare branches — standing in Deadvlei clay pan under a magnificent Milky Way. Towering red sand dunes of the Namib Desert framing the scene, star-lit sky reflecting off the cracked white clay surface. Deep blue sky transitioning to warm amber near the horizon. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 莫纳克亚山（Mauna Kea, 夏威夷）— 天文台黄昏
```
Stunning astrophotography of Mauna Kea Observatory, Hawaii, USA. Multiple telescope domes perched at 4207m summit, silhouetted against a twilight sky transitioning from deep orange at the horizon to star-filled indigo overhead. The first bright stars and planets appearing as the Milky Way begins to emerge. Sea of clouds below the summit creating an above-the-world feeling. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 阿里暗夜公园（Ali Dark Sky Park, 中国西藏）— 高原银河
```
Stunning astrophotography of Ali Dark Sky Park, Tibet, China. The vast Tibetan Plateau at 4200m altitude under an overwhelmingly brilliant Milky Way stretching from horizon to horizon. Snow-capped peaks of the Himalayas silhouetted along the southern horizon. Barren high-altitude terrain with sparse tundra vegetation in foreground. Extraordinary atmospheric transparency revealing countless faint stars. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 樱桃泉州立公园（Cherry Springs, 美国宾州）— 森林流星
```
Stunning astrophotography of Cherry Springs State Park, Pennsylvania, USA. A natural clearing in dense Appalachian old-growth forest, towering hemlock and cherry trees forming a dark frame around a brilliant star-filled sky. A bright meteor streaking across the Milky Way, leaving a vivid green-white trail. Fireflies glowing faintly among the tree line. Lush summer forest atmosphere meeting the cosmic spectacle above. Professional astrophotography quality, natural star colors, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | 名称 | 国家 | 标志性特征 |
|--------|------|------|------------|
| 1 | 阿塔卡马沙漠 | 智利 | ALMA 望远镜阵列与银河 |
| 2 | 纳米布兰德自然保护区 | 纳米比亚 | 死亡谷枯树与银河 |
| 3 | 莫纳克亚山天文台 | 美国（夏威夷） | 云海之上的天文台群 |
| 4 | 阿里暗夜公园 | 中国（西藏） | 高原银河全景 |
| 5 | 樱桃泉州立公园 | 美国（宾州） | 森林与流星 |
| 6 | 艾尔斯岩/乌鲁鲁 | 澳大利亚 | 红色巨岩与南天银河 |
| 7 | 特内里费岛泰德峰 | 西班牙 | 火山口上的星空 |
| 8 | 布莱斯峡谷 | 美国（犹他） | 石林之上的银河拱桥 |
| 9 | 凯里尼公园 | 爱尔兰 | 古老橡树林与极光 |
| 10 | 拉帕尔马岛穆查丘斯罗克天文台 | 西班牙 | 云海上的北欧光学望远镜 |

---

## 4. 潜水图鉴（Diving）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `diving_global.json` |
| 存储目录 | `data/diving_images/` |
| 命名规则 | `{id}.webp` |

### 视觉风格

专业水下摄影风格，展现清澈海水中的海洋生态系统之美。
阳光穿透水面形成放射状光线（God rays），珊瑚色彩鲜艳，海洋生物栩栩如生。
根据潜点特色，画面可聚焦于珊瑚花园、大型海洋动物、沉船遗址、洞穴/蓝洞等。
色调以蓝色和青绿色为基调，珊瑚和鱼群提供暖色对比。

### Prompt 模板

```
Professional underwater photograph at [潜点名英文], [国家]. [海洋生物/特征描述]. Crystal clear [tropical/temperate] water with natural sunlight rays penetrating from the surface, vibrant [coral/kelp/marine life] colors, rich aquatic detail. National Geographic underwater photography quality, ultra high resolution, 1792x1024, wide angle, no text no watermark
```

### 按潜水环境调整

| 环境类型 | 核心元素 | 氛围关键词 |
|----------|----------|------------|
| 珊瑚礁 | 硬珊瑚/软珊瑚群落、热带鱼群 | `vibrant coral garden, tropical reef fish, sunlit shallow water, color explosion` |
| 远洋/大型动物 | 鲸鲨、蝠鲼、锤头鲨群 | `open blue water, pelagic encounter, massive marine creature, awe-inspiring scale` |
| 蓝洞/洞穴 | 深蓝垂直光柱、钟乳石 | `deep blue abyss, vertical light shaft, cave formations, stalactites, otherworldly` |
| 沉船 | 船体残骸、珊瑚覆盖、鱼群穿梭 | `historic wreck encrusted with coral, schools of fish, time capsule, ghostly beauty` |
| 海藻森林 | 巨藻林、海獭、海豹 | `towering kelp forest, dappled sunlight, marine mammals, cathedral of green` |
| 冰下潜水 | 冰层下的蓝光、冰柱 | `ice diving, blue light filtering through ice, frozen cathedral, extreme cold water` |
| 裂缝/地质 | 板块裂缝、火山地形、清澈淡水 | `tectonic fissure, gin-clear glacial water, volcanic rock walls, geological wonder` |

### 示例 Prompt

#### 大堡礁（Great Barrier Reef, 澳大利亚）— 珊瑚花园与海龟
```
Professional underwater photograph at the Great Barrier Reef, Australia. A majestic green sea turtle gliding gracefully over a pristine coral garden — massive table corals, branching staghorn corals, and brain corals in vivid pink, purple, and green. Schools of colorful anthias and butterflyfish weaving through the reef. Crystal clear tropical water with golden sunlight rays penetrating from the surface, creating dappled patterns on the coral. National Geographic underwater photography quality, ultra high resolution, 1792x1024, wide angle, no text no watermark
```

#### 诗巴丹（Sipadan, 马来西亚）— 杰克鱼风暴
```
Professional underwater photograph at Sipadan Island, Malaysia. An enormous swirling tornado of thousands of chevron barracuda forming a perfect vortex column from reef to surface, a diver's silhouette visible through the spiraling silver wall of fish. Deep blue open water beyond, pristine coral reef drop-off below. Dramatic natural lighting creating metallic reflections off the barracuda scales. National Geographic underwater photography quality, ultra high resolution, 1792x1024, wide angle, no text no watermark
```

#### 伯利兹大蓝洞（Great Blue Hole, 伯利兹）— 航拍视角
```
Professional aerial photograph of the Great Blue Hole, Belize. A perfect circular deep-blue sinkhole 300 meters in diameter, surrounded by a ring of shallow turquoise water and white coral reef. The dramatic color contrast between the impossibly deep dark blue center and the vibrant light blue-green surrounding lagoon. Lighthouse Reef atoll stretching into the distance, Caribbean Sea shimmering. National Geographic style, ultra high resolution, 1792x1024, aerial perspective, no text no watermark
```

#### 拉贾安帕（Raja Ampat, 印度尼西亚）— 蝠鲼巡游
```
Professional underwater photograph at Raja Ampat, Indonesia. A giant oceanic manta ray with a wingspan of over 5 meters gliding majestically over a kaleidoscopic coral reef, remora fish attached to its belly. Below, the most biodiverse marine ecosystem on Earth — soft corals in every imaginable color, sea fans swaying in current, pygmy seahorses, nudibranchs. Crystal clear water with sunbeams creating a cathedral of light. National Geographic underwater photography quality, ultra high resolution, 1792x1024, wide angle, no text no watermark
```

#### 丝浮拉裂缝（Silfra, 冰岛）— 板块裂缝清水
```
Professional underwater photograph at Silfra Fissure, Thingvellir National Park, Iceland. Diving between the tectonic plates of North America and Eurasia — vertical walls of ancient lava rock covered in ethereal green and gold algae, separated by a narrow corridor of impossibly clear glacial water with over 100 meters visibility. Soft blue light filtering from above, creating a surreal alien landscape. The gin-clear water making the diver appear to float in air. National Geographic underwater photography quality, ultra high resolution, 1792x1024, wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | 名称 | 国家 | 标志性特征 |
|--------|------|------|------------|
| 1 | 大堡礁 | 澳大利亚 | 珊瑚花园与海龟 |
| 2 | 诗巴丹 | 马来西亚 | 杰克鱼/梭鱼风暴 |
| 3 | 伯利兹大蓝洞 | 伯利兹 | 完美圆形蓝洞 |
| 4 | 拉贾安帕 | 印度尼西亚 | 蝠鲼与最高生物多样性 |
| 5 | 丝浮拉裂缝 | 冰岛 | 板块裂缝清澈冰川水 |
| 6 | 马尔代夫 | 马尔代夫 | 鲸鲨与珊瑚环礁 |
| 7 | 帕劳 | 帕劳 | 水母湖无毒水母群 |
| 8 | 红海兄弟群岛 | 埃及 | 锤头鲨群与沉船 |
| 9 | 加拉帕戈斯群岛 | 厄瓜多尔 | 海鬣蜥与海狮 |
| 10 | 仙本那/马布岛 | 马来西亚 | 微距天堂（豆丁海马） |

---

## 5. 温泉图鉴（Hot Springs）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `hotspring_global.json` |
| 存储目录 | `data/hotspring_images/` |
| 命名规则 | `{id}.webp` |

### 视觉风格

蒸汽氤氲的氛围感摄影，展现温泉的矿物色彩和自然环境的和谐。
蒸汽是画面的灵魂——通过逆光或侧光让蒸汽层次分明，营造如梦似幻的意境。
水体颜色是核心视觉锚点——乳蓝、翡翠绿、铁锈红、硫磺黄各具特色。
自然环境与温泉的融合（雪景、森林、火山、荒原）增加画面张力。

### Prompt 模板

```
Photorealistic landscape photograph of [温泉名英文], [国家]. [特征描述]. Steam rising dramatically from [颜色] mineral-rich water, [周围环境描述]. [光线条件], atmospheric depth with steam layers. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 按温泉类型调整

| 类型 | 水色/特征 | 氛围关键词 |
|------|-----------|------------|
| 硅质温泉 | 乳白色/浅蓝色 | `milky blue-white water, silica deposits, ethereal glow, geothermal power` |
| 碳酸钙温泉 | 白色梯田/翡翠水 | `white travertine terraces, cascading mineral pools, turquoise water, geological art` |
| 铁质温泉 | 锈红色/橙色 | `rust-red iron-rich water, orange mineral deposits, blood-colored pools` |
| 硫磺温泉 | 黄色/灰绿色 | `sulfurous yellow deposits, boiling mud, volcanic gases, hellish landscape` |
| 多彩温泉 | 彩虹色环带 | `rainbow mineral rings, thermophilic bacteria mats, prismatic colors, alien beauty` |
| 森林温泉 | 自然融合 | `hidden forest pool, moss-covered rocks, steam through canopy, secret paradise` |
| 雪地温泉 | 冷暖对比 | `steam against snow, frozen landscape, extreme temperature contrast, winter serenity` |

### 示例 Prompt

#### 蓝湖温泉（Blue Lagoon, 冰岛）— 乳蓝蒸汽
```
Photorealistic landscape photograph of the Blue Lagoon, Iceland. Vast milky blue-white geothermal pool surrounded by black volcanic lava fields, thick billowing steam rising from the silica-rich water against a moody overcast Nordic sky. The otherworldly contrast between the vivid blue water, jet-black basalt rocks, and white steam clouds. Soft diffused light creating an ethereal, dreamlike atmosphere. Distant Svartsengi geothermal power plant partially obscured by steam. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 棉花堡（Pamukkale, 土耳其）— 白色梯田
```
Photorealistic landscape photograph of Pamukkale, Turkey. Stunning cascade of snow-white travertine terraces descending a hillside, each tier holding pools of vivid turquoise and teal mineral water. Warm golden sunset light raking across the calcite formations, creating deep shadows that reveal the intricate texture of the mineral deposits. Ancient ruins of Hierapolis visible on the hilltop above. Steam wisps rising from the warm thermal water. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 大棱镜温泉（Grand Prismatic Spring, 美国）— 彩虹航拍
```
Photorealistic aerial photograph of Grand Prismatic Spring, Yellowstone National Park, USA. The largest hot spring in America seen from directly above — a brilliant deep-blue center radiating outward through rings of vivid green, yellow, orange, and rust-red thermophilic bacterial mats. Thick white steam drifting across the surface, boardwalk trail visible at the edge for scale. Surrounding dark pine forest contrasting with the surreal alien colors. National Geographic style, ultra high resolution, 1792x1024, aerial perspective, no text no watermark
```

#### 腾冲热海（Tengchong Hot Sea, 中国云南）— 地热蒸谷
```
Photorealistic landscape photograph of Tengchong Hot Sea Geothermal Park, Yunnan, China. A dramatic volcanic valley with multiple boiling hot springs, fumaroles, and steaming vents erupting from the earth. The famous "Big Rolling Pot" — a natural cauldron of furiously boiling water at 97°C surrounded by mineral-stained rocks in yellow and orange. Thick columns of steam rising into the subtropical mountain forest canopy. Warm morning light filtering through the steam. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 別府地獄温泉（Beppu Hells, 日本）— 彩色地狱
```
Photorealistic landscape photograph of Beppu Jigoku Hell Hot Springs, Oita, Japan. The vivid cobalt-blue water of "Umi Jigoku" (Sea Hell) — an intensely colored boiling pool at 98°C, surrounded by tropical garden vegetation and Japanese stone lanterns. Dense white steam billowing from the vibrant blue surface, creating dramatic clouds against a clear sky. Traditional Japanese garden elements framing the supernatural blue pool. Rich contrast between the scalding azure water and lush green surroundings. National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | 名称 | 国家 | 标志性特征 |
|--------|------|------|------------|
| 1 | 蓝湖温泉 | 冰岛 | 乳蓝硅质水与黑色熔岩 |
| 2 | 棉花堡 | 土耳其 | 白色钙华梯田 |
| 3 | 大棱镜温泉 | 美国 | 彩虹色菌毯环带 |
| 4 | 腾冲热海 | 中国 | 沸腾大滚锅 |
| 5 | 別府地獄温泉 | 日本 | 彩色沸腾地狱 |
| 6 | 罗托鲁瓦 | 新西兰 | 毛利文化与地热 |
| 7 | 黄龙 | 中国 | 金黄钙华彩池 |
| 8 | 达洛尔 | 埃塞俄比亚 | 外星般的盐酸泉 |
| 9 | 地狱谷 | 日本（北海道） | 雪猴泡温泉（冬季） |
| 10 | 萨特尼亚 | 意大利 | 托斯卡纳瀑布温泉 |

---

## 6. 世界遗产（Heritage）

### 基本信息

| 项目 | 说明 |
|------|------|
| 数据源 | `heritage_global.json` |
| 存储目录 | `data/heritage_images/` |
| 命名规则 | `{id}.webp` |

### 视觉风格

建筑/文化摄影与自然风光摄影并重，展现遗产地的历史厚重感和视觉冲击力。
黄金时刻的暖色光线赋予古建筑生命力，蓝调时刻增添神秘感。
画面应传达"时间的重量"——古老建筑与自然环境的永恒对话。
注重建筑细节和整体环境的平衡，既展示宏伟规模又不失精妙工艺。

### Prompt 模板

```
Photorealistic photograph of [遗产地名英文], [国家]. [建筑/自然特征描述]. [光线时段] lighting casting [光影效果], dramatic sky, sense of historical grandeur and timeless beauty. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 按遗产类型调整

| 类型 | 核心元素 | 氛围关键词 |
|------|----------|------------|
| 古代神庙/宗教建筑 | 石雕细节、对称构图、朝圣氛围 | `ancient stone carvings, sacred geometry, spiritual atmosphere, weathered beauty` |
| 宫殿/城堡 | 宏伟立面、花园水景、皇家气度 | `royal grandeur, reflecting pools, ornate facades, imperial magnificence` |
| 古城/遗址 | 废墟美学、植被侵蚀、时间痕迹 | `atmospheric ruins, nature reclaiming stone, patina of centuries, archaeological wonder` |
| 自然遗产 | 地质奇观、原始生态 | `geological marvel, pristine ecosystem, natural wonder, Earth's masterpiece` |
| 文化景观 | 人与自然和谐、梯田、传统聚落 | `human-nature harmony, terraced landscape, traditional settlement, living heritage` |
| 工程奇迹 | 长城、运河、桥梁 | `monumental engineering, stretching to horizon, human determination, ancient technology` |

### 按文明/地区调整风格

| 文明/地区 | 视觉特征 |
|-----------|----------|
| 东南亚（吴哥/蒲甘） | 热带植被侵蚀石雕、晨雾中的塔林、温暖的砂岩色调 |
| 南亚（印度/尼泊尔） | 精美石雕、对称倒影、白色大理石、莫卧儿花园 |
| 中东/北非（佩特拉/金字塔） | 沙漠暖色调、玫瑰色岩壁、夕阳下的巨石 |
| 东亚（长城/故宫/京都） | 红色与金色、琉璃瓦、龙凤纹饰、四季变化 |
| 欧洲（古罗马/哥特式） | 灰白石材、彩色玻璃窗、鹅卵石广场、雨后光泽 |
| 中南美（马丘比丘/奇琴伊察） | 阶梯金字塔、云雾缭绕、丛林包围、失落文明感 |

### 示例 Prompt

#### 吴哥窟（Angkor Wat, 柬埔寨）— 日出倒影
```
Photorealistic photograph of Angkor Wat, Siem Reap, Cambodia. The iconic five lotus-bud towers of the 12th-century Khmer temple silhouetted against a spectacular sunrise sky in deep orange, pink, and purple gradients. Perfect mirror reflection in the rectangular moat creating a flawless symmetrical composition. Palm trees framing the scene, morning mist hovering over the water surface. Golden light beginning to illuminate the intricate bas-relief carvings on the sandstone walls. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 马丘比丘（Machu Picchu, 秘鲁）— 晨雾圣城
```
Photorealistic photograph of Machu Picchu, Peru. The ancient Inca citadel perched dramatically on a narrow ridge between Huayna Picchu and Machu Picchu mountain peaks, morning mist swirling through the Urubamba River valley far below. Precise Inca stonework of terraces, temples, and residences glowing warm in the first golden rays of sunrise. Lush green tropical vegetation surrounding the archaeological site. Dramatic Andean cloud formations framing the sacred city. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 泰姬陵（Taj Mahal, 印度）— 黎明倒影
```
Photorealistic photograph of the Taj Mahal, Agra, India. The pristine white Mughal marble mausoleum with its iconic central dome and four minarets, bathed in the soft pink-gold light of dawn. Perfectly symmetrical reflection in the long rectangular reflecting pool along the central axis, flanked by dark cypress trees and Mughal garden pathways. Delicate pietra dura inlay work visible on the marble surface, translucent quality of the white marble glowing in morning light. Wisps of mist rising from the Yamuna River behind. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 长城（Great Wall, 中国）— 秋色长城
```
Photorealistic photograph of the Great Wall of China at Jinshanling section, Beijing/Hebei, China. The ancient stone wall snaking dramatically across steep mountainous terrain, watchtowers punctuating the ridgeline at regular intervals, stretching into the misty distance. Blazing autumn foliage — fiery red, orange, and golden leaves of the surrounding deciduous forest contrasting with the grey stone fortification. Warm golden hour side lighting creating long shadows and revealing the texture of every stone. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

#### 佩特拉（Petra, 约旦）— 玫瑰古城
```
Photorealistic photograph of the Treasury Al-Khazneh at Petra, Jordan. The magnificent Nabataean rock-cut facade carved directly into the rose-red sandstone cliff face, intricate Hellenistic columns and sculptures weathered by two millennia. Warm afternoon sunlight streaming through the narrow Siq canyon entrance, illuminating the lower portion of the facade in brilliant gold-pink while the upper stories remain in cool shadow. Natural bands of red, pink, orange, and cream in the sandstone creating nature's own color palette. Professional travel photography, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 优先生成列表（Top 10）

| 优先级 | 名称 | 国家 | 标志性特征 |
|--------|------|------|------------|
| 1 | 吴哥窟 | 柬埔寨 | 五塔日出倒影 |
| 2 | 马丘比丘 | 秘鲁 | 云雾中的印加圣城 |
| 3 | 泰姬陵 | 印度 | 黎明白色大理石倒影 |
| 4 | 长城（金山岭） | 中国 | 秋色山脊蜿蜒 |
| 5 | 佩特拉 | 约旦 | 峡谷中的玫瑰宝库 |
| 6 | 吉萨金字塔 | 埃及 | 夕阳下的大金字塔与狮身人面像 |
| 7 | 罗马斗兽场 | 意大利 | 蓝调时刻的古竞技场 |
| 8 | 故宫 | 中国 | 雪后紫禁城金色琉璃瓦 |
| 9 | 圣索菲亚大教堂 | 土耳其 | 金色穹顶与宣礼塔 |
| 10 | 巴甘寺庙群 | 缅甸 | 日出热气球与万塔之城 |

---

## 附录：批量生成工作流

### 1. 生成步骤

1. 从对应的 `*_global.json` 读取条目列表
2. 按优先级排序，先生成 Top 10
3. 根据条目信息（名称、位置、特征）填充 Prompt 模板
4. 调用图片生成 API，参数：
   - 尺寸：`1792x1024`
   - 格式：WebP
   - 质量：`high`
5. 保存到对应目录，文件名为 `{id}.webp`

### 2. 质量检查清单

- [ ] 图片尺寸是否为 1792×1024
- [ ] 是否为 WebP 格式
- [ ] 画面是否具有真实摄影感（非 AI 绘画风格）
- [ ] 是否正确展现该地点的标志性特征
- [ ] 是否无文字、水印或人工元素
- [ ] 色彩是否自然丰富（非过度饱和）
- [ ] 构图是否有前中后景层次
- [ ] 光影是否自然且有戏剧性

### 3. 目录结构总览

```
data/
├── mountain_images/     # 雪山图鉴
│   ├── {id}.webp
│   └── README.md
├── park_images/         # 国家公园
│   └── {id}.webp
├── darksky_images/      # 暗夜星空
│   └── {id}.webp
├── diving_images/       # 潜水图鉴
│   └── {id}.webp
├── hotspring_images/    # 温泉图鉴
│   └── {id}.webp
├── heritage_images/     # 世界遗产
│   └── {id}.webp
└── image_prompts.md     # 本指南文件
```
