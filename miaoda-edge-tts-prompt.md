# 妙搭 Edge TTS 接入 Prompt

请用 edge-tts 实现文字转语音，生成可在线播放和下载的 MP3，不要只做模拟界面。

这是 Python 开源库，项目地址：
https://github.com/rany2/edge-tts

安装：
```bash
pip install edge-tts
```

Python 调用示例：
```python
import asyncio
import edge_tts

async def main():
    tts = edge_tts.Communicate(
        text="加油！终点就在前面！稳住呼吸，向前冲！",
        voice="zh-CN-shaanxi-XiaoniNeural",
        rate="+20%",
        pitch="+4Hz",
        volume="+10%"
    )
    await tts.save("output.mp3")

asyncio.run(main())
```

需要支持三个声线：
- 晓妮（陕西女声）：zh-CN-shaanxi-XiaoniNeural
- 晓北（辽宁女声）：zh-CN-liaoning-XiaobeiNeural
- 台湾女生：zh-TW-HsiaoChenNeural

页面提供文案输入、声线选择、语速调整、生成按钮、音频播放器和下载按钮。

注意：
1. edge-tts 必须在服务端运行并联网，不需要 Azure API Key。
2. 它没有独立情绪参数；冲刺感通过文案、语速和音调调整。
3. 生成的 MP3 必须提供浏览器可访问的地址，不能返回服务器本地路径。
4. 先验证你的环境能否安装和运行 edge-tts，并实际生成一段音频。
5. 如果妙搭不能运行 Python，就需要外部 Python HTTP 服务；请明确告诉我缺什么，不要编造接口或用固定音频冒充合成结果。

先读取项目 README，再按实际运行环境实现。
