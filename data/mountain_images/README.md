# 雪山图片生成规范

## 文件规范
- 路径: `data/mountain_images/{id}.webp`
- 尺寸: **1792×1024px**（7:4 宽幅，与遗迹图保持一致）
- 格式: WebP
- 命名: 使用 mountains_global.json 中的 id，如 `1.webp`（珠穆朗玛峰）

## 视觉风格

**真实摄影风格，风光大片质感**

| 要素 | 标准 |
|------|------|
| 风格 | 高清真实摄影风格（Photorealistic），类似国家地理杂志的风光摄影 |
| 视角 | 远景或中远景，完整展示山峰全貌和周围环境 |
| 构图 | 山峰主体占画面 40%~60%，留出天空和前景层次感 |
| 光影 | 黄金时刻（Golden Hour）或蓝调时刻（Blue Hour）光线，侧光突出山体立体感 |
| 天空 | 有层次的天空——晚霞/朝霞渐变色，或高海拔深蓝天空配卷云 |
| 雪山 | 雪线清晰，冰川纹理可见，岩壁和积雪对比分明 |
| 前景 | 根据环境搭配：冰碛湖、高山草甸、针叶林、云海、经幡等 |
| 色调 | 冷暖对比——山体冰蓝冷色调，天空或光线带暖色 |
| 氛围 | 壮观、敬畏、宁静的自然感 |

## Prompt 模板

```
Photorealistic landscape photograph of [山名英文], [海拔]m, [所在地区], majestic snow-capped peak with visible glaciers and ice ridges, golden hour dramatic side lighting, layered composition with [前景元素] in foreground, crisp detail on snow and rock textures, deep blue sky with wispy clouds, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

## 按类型调整前景和氛围

| 类型 | 前景元素 | 氛围关键词 |
|------|----------|------------|
| 极高峰(8000m+) | 冰碛、乱石坡、远方云海 | `extreme altitude, thin atmosphere, wind-blown snow plumes, deep blue sky` |
| 高峰(7000m+) | 冰川末端、冰塔林 | `massive glaciers, seracs, dramatic cloud formations` |
| 著名雪山 | 湖泊倒影、森林、草甸 | `iconic silhouette, mirror lake reflection, alpine meadows` |
| 经典雪山 | 帐篷营地、登山者剪影 | `mountaineering atmosphere, base camp tents, prayer flags` |
| 火山雪峰 | 樱花/热带植被、城市远景 | `volcanic cone, symmetrical shape, cultural landscape foreground` |
| 禁登神山 | 寺庙、经幡、晨雾 | `sacred untouched peak, mystical clouds, prayer flags, morning mist` |

## 按地区调整环境

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

## 示例 Prompt

### 珠穆朗玛峰 (id=1, 极高峰, 8849m)
```
Photorealistic landscape photograph of Mount Everest, 8849m, Himalayas Nepal-Tibet border, towering snow-capped pyramid peak with wind-blown snow plumes at summit, massive Khumbu glacier and icefall visible, golden hour dramatic side lighting from the west, layered composition with rocky moraine and prayer flags in foreground, deep indigo sky at extreme altitude, thin atmosphere haze, crisp detail on ice ridges and rock bands, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 富士山 (id=91, 火山雪峰, 3776m)
```
Photorealistic landscape photograph of Mount Fuji, 3776m, Japan, perfectly symmetrical volcanic cone with snow-capped summit, golden hour warm light, layered composition with Chureito Pagoda and cherry blossoms in foreground, Lake Kawaguchi mirror reflection, soft pink and orange sky gradients, iconic Japanese landscape, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 梅里雪山 (id=42, 禁登神山, 6740m)
```
Photorealistic landscape photograph of Meili Snow Mountain Kawagebo Peak, 6740m, Yunnan China, sacred unclimbed peak emerging from dramatic swirling clouds, golden morning light illuminating the snow-covered summit while lower slopes remain in shadow, Tibetan prayer flags and Feilai Temple in foreground, mystical atmosphere with cloud sea in Mekong valley below, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 马特洪峰 (id=78, 著名雪山, 4478m)
```
Photorealistic landscape photograph of the Matterhorn, 4478m, Swiss Alps Zermatt, iconic pyramidal peak with sharp ridges and snow-covered faces, blue hour twilight with alpenglow on summit, perfect reflection in Riffelsee alpine lake in foreground, surrounding Alpine peaks and glaciers, crisp mountain air atmosphere, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

### 贡嘎山 (id=30, 高峰, 7556m)
```
Photorealistic landscape photograph of Mount Gongga Minya Konka, 7556m, Sichuan China, massive glaciated peak towering above cloud sea, dramatic side lighting at sunrise, layered composition with subalpine rhododendron forest and Hailuogou glacier in foreground, Tibetan plateau atmosphere, National Geographic style, ultra high resolution, 1792x1024, cinematic wide angle, no text no watermark
```

## 生成优先级

先生成 10 座标志性雪山：

| 优先级 | id | 名称 | 海拔 | 类型 |
|--------|-----|------|------|------|
| 1 | 1 | 珠穆朗玛峰 | 8849m | 极高峰 |
| 2 | 2 | 乔戈里峰 K2 | 8611m | 极高峰 |
| 3 | 30 | 贡嘎山 | 7556m | 高峰 |
| 4 | 42 | 梅里雪山 | 6740m | 禁登 |
| 5 | 91 | 富士山 | 3776m | 火山雪峰 |
| 6 | 78 | 马特洪峰 | 4478m | 著名雪山 |
| 7 | 19 | 南迦巴瓦峰 | 7782m | 高峰 |
| 8 | 50 | 玉龙雪山 | 5596m | 著名雪山 |
| 9 | 85 | 乞力马扎罗山 | 5895m | 著名雪山 |
| 10 | 76 | 勃朗峰 | 4809m | 著名雪山 |

然后按 id 顺序批量生成剩余山峰。
