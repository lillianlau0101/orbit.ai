miniprogram/
├── app.js                 # 全局逻辑
├── app.json               # 全局配置
├── app.wxss               # 全局样式
├── cloudfunctions/        # 云函数目录
│   ├── aiChat/           # AI对话云函数（调用腾讯混元）
│   ├── getMoodStats/     # 获取统计数据
│   └── config/           # 配置中心（存放API密钥）
├── components/           # 复用组件
│   ├── moodPicker/       # 情绪选择器组件
│   ├── intensitySlider/  # 强度滑块组件
│   └── ec-canvas/        # ECharts组件（需下载）
├── pages/
│   ├── index/            # 首页（入口+今日概览）
│   ├── moodRecord/       # 情绪记录页
│   ├── moodChat/         # AI对话页（基于刚记录的情绪）
│   ├── journal/          # 日记列表（时间轴）
│   ├── journalEdit/      # 日记编辑（早/晚）
│   └── statistics/       # 数据可视化页
├── utils/
│   ├── db.js             # 数据库操作封装
│   ├── ai.js             # AI相关工具
│   └── date.js           # 日期处理
└── static/
    ├── images/           # 本地图片
    └── emotions/         # 情绪图标
