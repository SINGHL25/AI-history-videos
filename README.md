# AI-history-videos

# AI-Generated History Shorts 🇮🇳

This project generates realistic AI-characterized educational videos for YouTube using:
- AI voice narration (gTTS or ElevenLabs)
- Image/Character animation (optional)
- MoviePy for video assembly

## Folder Format
Each episode (e.g., Dandi March, Revolt 1857) has:
- `script.txt` — narration content
- `voiceover.mp3` — audio narration
- `subtitles.srt` — synced subtitles
- `movie.py` — assembles final `video.mp4`

ai-history-videos/
├── 01_dandi_march/
│   ├── script.txt
│   ├── voiceover.mp3
│   ├── subtitles.srt
│   ├── movie.py
│   ├── video.mp4  ← (final output)
│   └── assets/
│       ├── background.jpg
│       └── character.png
├── 02_revolt_1857/
│   ├── script.txt
│   ├── voiceover.mp3
│   ├── subtitles.srt
│   ├── movie.py
│   ├── video.mp4
│   └── assets/
├── README.md
├── requirements.txt
└── utils/
    ├── text_to_speech.py
    ├── srt_generator.py
    └── ai_character.py


## How to Run
1. Install requirements:
pip install -r requirements.txt

cpp
Copy
Edit
2. Generate voiceover using:
python utils/text_to_speech.py 01_dandi_march/script.txt

markdown
Copy
Edit
3. Generate subtitles:
python utils/srt_generator.py 01_dandi_march/voiceover.mp3

css
Copy
Edit
4. Generate video:
python 01_dandi_march/movie.py

markdown
Copy
Edit

## Output
- Upload-ready video in `video.mp4`
🧠 Suggested Episode Plan (Indian History Series)
Ep. No	Title	File Folder	Notes
1	Dandi March	01_dandi_march	Gandhi’s salt protest
2	Revolt of 1857	02_revolt_1857	Mangal Pandey, Rani Laxmi
3	Partition of Bengal (1905)	03_bengal_partition	Lord Curzon, Swadeshi
4	Jallianwala Bagh Massacre	04_jallianwala	General Dyer
5	Quit India Movement	05_quit_india	1942 Congress revolution
6	Role of Subhas Chandra Bose	06_subhas_bose	INA, Azad Hind
7	Independence & Partition (1947)	07_independence	Mountbatten Plan, Gandhi

🛠 How You Can Proceed
Finalize the Script: Write the script.txt for each topic (~60–90 seconds for shorts).

Voiceover: Use gTTS or AI voice (ElevenLabs) to generate voiceover.mp3.

Subtitles: Auto-generate .srt using timestamps from voiceover.

Video Assembly: Use MoviePy (movie.py) to combine background, character, voiceover, subtitles.

(Optional): Use AI-generated characters (e.g., via D-ID, HeyGen, Synthesia) for speaking avatar overlays.

Publish to YouTube: Include proper title, hashtags, and short description per video.

📽️ Sample movie.py
python
Copy
Edit
from moviepy.editor import *

# Load components
bg = ImageClip("assets/background.jpg").set_duration(60)
audio = AudioFileClip("voiceover.mp3")
subtitles = SubtitlesClip("subtitles.srt", lambda txt: TextClip(txt, fontsize=30, color='white'))
character = ImageClip("assets/character.png").resize(height=400).set_duration(60).set_pos(("center", "bottom"))

# Combine
final = CompositeVideoClip([bg, character, subtitles.set_pos(("center", "bottom"))])
final = final.set_audio(audio)
final.write_videofile("video.mp4", fps=24)

🔧 1. Script to Voiceover (Text-to-Speech)
✅ ElevenLabs – Best free realistic voice
Upload or type your script → get high-quality voiceover (voiceover.mp3)

Free plan available (limited credits)

Languages: Multiple Indian English accents available

Alternative: PlayHT, TTSMP3.com

🎥 2. Avatar Generation for Character
✅ D-ID – Talking photo from audio
Upload character.png + voiceover.mp3 → animated speaking character

Good for Narrator clips

Free sign-up with limited usage

Alternative: HeyGen (limited free export)

🎬 3. Video Editor (combine audio, images, overlays)
✅ [MoviePy (Python-based) – Local/scripted video**
You already have movie.py script

Combines: background.jpg, intro_logo.png, voiceover.mp3, subtitles.srt, etc.

Free, customizable, offline

Alternative GUI editors (free):

CapCut Web

Clipchamp

WeVideo

📄 4. Subtitles Generator (auto or manual)
✅ Kapwing Subtitles Tool
Upload script or video, it auto-generates .srt

Allows manual editing and export as .srt or burned-in

Alternative: SubtitleCat, Happy Scribe

🖼️ 5. Background & Scene Images
✅ Unsplash or Pixabay
Get royalty-free images for historical backdrops (background.jpg)

Use keywords like “India 1947”, “Gandhi protest”, etc.

Alternative: Pexels

🎵 6. Background Music
✅ Free Music Archive or Bensound
Royalty-free music, sorted by mood or theme

Format: .mp3 usable in movie.py or video editors

Keywords: “Epic India”, “Emotional”, “Cinematic”

🎞️ 7. Final Export and Sharing
✅ Canva Video Editor (Beginner-friendly)
Free for basic video edits, overlays, timeline, titles

Great if you want to visually edit + download video.mp4

Alternative: OpenShot – open-source desktop editor

📦 OPTIONAL: All-in-One Web App (drag & drop everything)
✅ Renderforest
Upload assets + use templates (Intro/Outro, text overlays, scenes)

Free plan with watermark (can export low-res free)

Ideal for complete end-to-end storytelling videos
