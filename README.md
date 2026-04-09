# Gemma 4 E2B — In-Browser Chat

A single HTML file that runs Google's [Gemma 4 E2B](https://huggingface.co/google/gemma-4-E2B-it) model entirely in your browser via WebGPU. No server, no API keys, no data leaves your machine.

## Features

- **Fully offline** — model weights are cached after first download (~1.5 GB)
- **Multimodal** — supports text, image, and audio input
- **Streaming** — tokens appear as they're generated with tok/s counter
- **Zero dependencies** — one `index.html` file, no build step
- **Private by design** — everything runs locally in your browser tab

## Usage

1. Open `index.html` in **Chrome 113+** or **Edge 113+** (WebGPU required)
2. Wait for the model to download (~1.5 GB on first load, cached after that)
3. Start chatting

### Attach files

- Click the **+** button to attach images or audio
- **Drag and drop** files onto the page
- **Paste** images from your clipboard (Ctrl/Cmd+V)

## Performance

| Device | Tokens/sec |
|---|---|
| MacBook Pro M3 | ~20-25 |
| RTX 3060 laptop | ~30 |

## How it works

The app loads the [ONNX-quantized](https://huggingface.co/onnx-community/gemma-4-E2B-it-ONNX) (q4f16) version of Gemma 4 E2B using [@huggingface/transformers](https://huggingface.co/docs/transformers.js) and runs inference on your GPU through the browser's WebGPU API.

## Requirements

- Chrome 113+ or Edge 113+ with WebGPU enabled
- A GPU with enough VRAM (~2 GB)
- ~1.5 GB disk/network for the initial model download

## License

MIT
