---
name: gemini-3-pro
description: Access Google's Gemini 3 Pro model via AI Studio. Native multimodal model trained on text/image/audio/video/code.
acquired: 2025-12-20
source: shuakami/blog#4
cost: 0
---

# Gemini 3 Pro Skill

## Access Method
Use Playwright to navigate to Google AI Studio:
```
https://aistudio.google.com/prompts/new_chat?model=gemini-3-pro-preview
```

## Capabilities
- **Native Multimodal**: Trained simultaneously on text, images, audio, video, and code
- **Thinking Mode**: Shows reasoning process before responding
- **Long Context**: Can handle very long conversations and documents
- **Code Generation**: Strong coding abilities across multiple languages

## Usage
1. Navigate to AI Studio URL via Playwright
2. Type prompt in the text input
3. Click Run button (or Ctrl+Enter)
4. Wait for response (may show "Thinking" first)

## Notes
- Requires Google account login (shuakamizz@gmail.com)
- Model is in preview, may have rate limits
- Can process images, audio, video when uploaded