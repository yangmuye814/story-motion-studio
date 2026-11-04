# 中文配音候选与接入边界

调研日期：2026-11-04；这是候选调研，不代表已经安装、适配Windows或试听通过
默认无配音保持不变，大模型不加入视频技能的一键基础安装

## 本机已有技能入口

- media-use：HyperFrames素材、旁白与混音入口，提供本地Kokoro路线及HeyGen路线；当前固定运行时的可用能力需实测，不能把HeyGen免费额度当作永久免费服务
- wtt-code-animation-studio：已有voice.py和Qwen3-TTS配置管理；当前适配为Apple Silicon的MLX，不能在Windows直接当作可用后端
- huashu-art-motion：语音方案与模型核查入口；核查资料不等于通用合成适配器已完成

## 模型候选

| 模型 | 可考虑用途 | 当前状态 |
|---|---|---|
| Qwen3-TTS | 中文讲解、多预设音色；按具体版本选择声音设计或克隆 | 官方有0.6B/1.7B系列，需独立Windows推理验证 |
| CosyVoice | 中文自然表达与参考音色路线 | 官方推荐Fun-CosyVoice3-0.5B，依赖和音色需单独验证 |
| VoxCPM | 关注自然韵律与可控表达 | VoxCPM2支持声音设计与可控克隆，体量更大；可按机器条件比较旧小型号 |

这些项目可选择开源本地路线，但仍需本机算力、模型下载与各模型许可核对，不保证无AI感或演员表现
不要按参数量直接承诺显存够用、速度或音质，也不要假定苹果MLX包可在Windows运行

## 建议制作顺序

先选20–30秒真实中文讲稿做试听，再决定模型与音色
术语、英文缩写和数字单独维护读法，文稿标停顿、重音和情绪；不以克隆音色代替表演设计
生成分段WAV后测真实时长，再调整同一份分镜和阅读停留，加入HyperFrames音轨
旁白出现时降低BGM，最终实际试听，不能以音量分析代替听感验收
未经用户要求不自动下载模型、不启用付费API、不更改默认无配音

## 官方来源

- https://github.com/QwenLM/Qwen3-TTS
- https://github.com/QwenAudio/CosyVoice
- https://github.com/OpenBMB/VoxCPM
- https://openbmb.cn/docs/en/guides/voxcpm/
