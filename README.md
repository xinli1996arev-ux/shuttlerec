# 🚌 下班哪儿去

> Shunyi to Everywhere — 顺义班车线路推荐

输入目的地，自动推荐最佳班车线路 + 备选方案 + 最后一公里出行指引。

## 功能

- 输入任意北京地址，智能匹配最佳下车点和班车线路
- 27 条线路覆盖北京各方向，来自顺义鑫桥中路3号院
- 两阶段距离算法：Haversine 粗筛 + 高德步行 API 精算
- 驾车路径拟合：显示真实道路轨迹
- 最后一公里指引：≤500m 步行 / 500m–3km 骑行 / >3km 公交
- 地图全览模式：所有线路 + 终点站标签，选中后高亮切换

## 技术栈

- 单文件 HTML，零构建，零依赖
- 高德 JS API v2.0
- Python 校准脚本处理坐标

## 本地运行

```bash
cd shuttlerec
python3 -m http.server 8765
# 打开 http://localhost:8765
```

## 文件说明

| 文件 | 说明 |
|---|---|
| `index.html` | 主应用 |
| `index_v1.html` | v1 版本备份 |
| `起点.png` | 起点标记图标 |
| `stations_final.json` | 校准后站点坐标 |
| `build_final.py` | 坐标校准脚本 |
| `calibrate_coords.py` | 自动校准（前后站点插值） |
| `collect_coords.html` | 浏览器端坐标采集工具 |
