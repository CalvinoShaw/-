# 使用本地战锤40K图片的指南

## 方案1：使用本地图片文件夹

### 步骤1：准备图片
1. 创建一个 `images` 文件夹在项目根目录
2. 将你的战锤40K图片放入该文件夹
3. 图片命名为：`wh40k_1.jpg`, `wh40k_2.jpg`, 等等

### 步骤2：修改代码
在 `index.html` 中修改 `generateImageUrls()` 函数：

```javascript
// 使用本地图片
function generateImageUrls() {
    const urls = [];
    const imageCount = 100; // 你有多少张图片

    for (let i = 0; i < imageCount; i++) {
        urls.push({
            id: i + 1,
            keyword: 'local',
            sources: [
                `./images/wh40k_${i + 1}.jpg`,
                `./images/wh40k_${i + 1}.png`,
                // 备选占位符
                `https://via.placeholder.com/800x600/1a1a2e/eee?text=Warhammer+40K+${i + 1}`,
            ]
        });
    }

    return urls;
}
```

## 方案2：使用官方/合法资源

### 推荐的合法图片来源：

1. **Warhammer Community官网**
   - https://www.warhammer-community.com/
   - 下载官方壁纸和艺术作品（仅供个人使用）

2. **Steam Workshop**
   - Warhammer游戏的官方截图和艺术作品

3. **Wikimedia Commons**
   - https://commons.wikimedia.org/
   - 搜索 "Warhammer 40000" 找到开放许可的图片

4. **Flickr Creative Commons**
   - https://www.flickr.com/creativecommons/
   - 搜索战锤相关内容，选择CC授权的图片

5. **DeviantArt**
   - 很多艺术家分享战锤同人作品
   - 需要获得艺术家许可

## 方案3：使用图片URL列表

如果你已经有合法的图片URL列表：

```javascript
const warhammer40kImages = [
    'https://example.com/legal-wh40k-image-1.jpg',
    'https://example.com/legal-wh40k-image-2.jpg',
    // ... 更多URL
];

function generateImageUrls() {
    return warhammer40kImages.map((url, i) => ({
        id: i + 1,
        keyword: 'warhammer 40k',
        sources: [url]
    }));
}
```

## 方案4：使用公开API

### Pexels API (免费)
1. 注册获取API Key: https://www.pexels.com/api/
2. 使用API搜索相关主题

```javascript
// 示例：使用Pexels API
const PEXELS_API_KEY = 'YOUR_API_KEY';

async function searchPexelsImages(query) {
    const response = await fetch(
        `https://api.pexels.com/v1/search?query=${query}&per_page=80`,
        {
            headers: {
                'Authorization': PEXELS_API_KEY
            }
        }
    );
    const data = await response.json();
    return data.photos.map(photo => photo.src.large);
}
```

### Pixabay API (免费)
- https://pixabay.com/api/docs/
- 类似的API调用方式

## 重要提醒

⚠️ **版权声明**：
- 所有战锤40K官方图片版权归Games Workshop所有
- 使用任何图片前请确认授权许可
- 本项目仅供学习和演示使用
- 不得用于商业用途

📝 **合法使用准则**：
1. 优先使用自己拍摄的模型照片
2. 使用官方提供的免费资源
3. 使用CC授权或公共领域图片
4. 获得艺术家明确许可
5. 遵守Fair Use原则（教育/评论用途）

## 最佳实践建议

如果你有战锤40K的模型：
1. **自己拍照**：拍摄你的战锤模型收藏
2. **制作教程**：展示涂装过程
3. **战报记录**：拍摄游戏过程

这样的内容完全合法，而且更有个人特色！

---

⚔️ **For the Emperor!** ⚔️
