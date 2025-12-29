# Google Image Gen API Starter

Generate images with Google's Gemini API.

`uv` is required to easily install dependencies.

Video Guide: 

## Setup

```bash
# Get API key from https://aistudio.google.com/apikey
# Paid tier is recommended to avoid continuous limits
echo "GOOGLE_AI_API_KEY=your_key_here" > .env
uv sync
```

## Usage

```bash
# Basic
uv run python main.py output.png "A 3D cube on black background"

# With style template (see styles/blue_glass_3d.md)
uv run python main.py output.png "gear icon" --style styles/blue_glass_3d.md

# Multiple subjects
uv run python main.py output.png "cube" "sphere" "pyramid" --style styles/blue_glass_3d.md

# Edit existing image
uv run python main.py output.png "Make it green" --edit input.png

# With reference image
uv run python main.py output.png "Same style" --ref example.png

# Different aspect ratio
uv run python main.py output.png "Prompt" --aspect 1:1
```

## Options

See `main.py` for full parameter documentation.

```
--style, -s    Style template .md file with prompt template
--ref, -r      Reference image (repeatable)
--edit, -e     Image to edit
--aspect, -a   1:1, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9
```

## Style Templates

The `--style` flag reads a prompt template from a markdown file and inserts your subject:

```bash
# Instead of typing the full prompt every time
uv run python main.py output.png "gear icon" --style styles/blue_glass_3d.md
```

Create your own by copying `styles/blue_glass_3d.md` and editing the `## Prompt Template` section. Use `{subject}` as the placeholder.

## Showcase

`showcase/` contains example outputs and demonstrates:
- `examples/` - Blue glass style outputs
- `gradient_degradation/` - Why to avoid gradients when iterating
- `backgrounds/` - Separately generated backgrounds for compositing
