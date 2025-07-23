# 🎨 Pancha Charcha - AI Creative Studio

**Pancha Charcha** is a comprehensive AI-powered creative platform that enables users to generate music, videos, cover art, stories, and podcasts using cutting-edge artificial intelligence technology.

## ✨ Features

### 🎵 Music Generation
- Create original songs from text descriptions
- Support for multiple genres (Pop, Rock, Jazz, Classical, Electronic, Hip Hop, Country, Folk)
- Customizable mood and duration settings
- AI-generated lyrics and musical arrangements

### 🎬 Video Generation
- Transform text prompts into stunning videos
- Multiple visual styles (Realistic, Animated, Cartoon, Cinematic, Abstract)
- Customizable duration (5-30 seconds)
- Scene-by-scene breakdowns and visual compositions

### 🎨 Cover Art Generation
- Professional album covers, book covers, and artwork
- Multiple design styles (Modern, Vintage, Minimalist, Abstract, Photorealistic)
- Support for different cover types (Album, Book, Podcast, Poster)
- AI-powered visual design concepts

### 📚 Story Generation
- Creative writing assistance for multiple genres
- Flexible story lengths (Short, Medium, Long)
- Genre-specific elements (Fantasy, Sci-Fi, Mystery, Romance, Thriller, Adventure, Drama)
- Complete narrative structures with characters and plot development

### 🎙️ Podcast Generation
- AI-generated podcast scripts and audio
- Multiple formats (Interview, Monologue, Discussion, Storytelling, Educational)
- Customizable voice styles and duration
- Complete transcripts and production notes

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip (Python package installer)
- API keys for the services you want to use:
  - **OpenRouter API key** (required) - [openrouter.ai](https://openrouter.ai/keys)
  - **ElevenLabs API key** (for audio generation) - [elevenlabs.io](https://elevenlabs.io/)
  - **Stability AI API key** (for image generation) - [platform.stability.ai](https://platform.stability.ai/)
  - **Replicate API token** (for video generation) - [replicate.com](https://replicate.com/account/api-tokens)

### Installation

1. **Clone or download the project**
   ```bash
   cd pancha-charcha
   ```

2. **Set up your API keys**
   - Open `.env.local` file
   - Replace the placeholder values with your actual API keys:
   ```env
   # Required for all AI text generation
   OPENROUTER_API_KEY=your_actual_openrouter_api_key_here
   
   # Optional: For high-quality audio generation
   ELEVENLABS_API_KEY=your_actual_elevenlabs_api_key_here
   
   # Optional: For image generation
   STABILITY_API_KEY=your_actual_stability_api_key_here
   
   # Optional: For video generation
   REPLICATE_API_TOKEN=your_actual_replicate_api_token_here
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Start the server**
   ```bash
   # Make the start script executable (Linux/Mac)
   chmod +x start.sh
   ./start.sh
   
   # Or run directly with Python
   python server.py
   ```

5. **Open your browser**
   Navigate to `http://localhost:8000`

## 🔧 Configuration

### Environment Variables

Edit the `.env.local` file to customize your setup:

```env
# Required: Your OpenRouter API key
OPENROUTER_API_KEY=your_openrouter_api_key_here

# Optional: Server configuration
PORT=8000
HOST=0.0.0.0
FLASK_ENV=development

# Optional: AI model configuration
DEFAULT_MODEL=openai/gpt-4o
TEMPERATURE=0.8
MAX_TOKENS=2000
```

### Supported AI Models

The platform uses OpenRouter to access various AI models:
- `openai/gpt-4o` (default) - Best overall performance
- `anthropic/claude-3-sonnet` - Excellent for creative writing
- `meta-llama/llama-3.1-8b-instruct` - Fast and efficient
- `google/gemini-pro` - Good for multimodal tasks

## 🎯 Usage Guide

### Creating Content

1. **Quick Start**: Enter a prompt in the main search bar and click "Create Now"
2. **Specific Tools**: Click on individual feature cards (Music, Video, Cover Art, Story, Podcast)
3. **Customization**: Use the detailed options in each creator modal
4. **Download**: Save your generated content using the download buttons

### Example Prompts

**Music Generation:**
- "Create an upbeat pop song about summer adventures"
- "Generate a melancholic jazz piece for a rainy evening"
- "Compose an energetic workout anthem with electronic beats"

**Video Generation:**
- "A cinematic sunset over a mountain landscape"
- "Animated sequence of a cat chasing butterflies in a garden"
- "Abstract visualization of music with flowing colors"

**Cover Art:**
- "Minimalist album cover for an indie rock band"
- "Fantasy book cover featuring a dragon and castle"
- "Modern podcast cover for a technology discussion show"

**Story Generation:**
- "A sci-fi adventure about time travel and parallel universes"
- "A romantic comedy set in a small coastal town"
- "A mystery thriller involving a missing painting"

**Podcast Generation:**
- "Educational episode about renewable energy technologies"
- "Interview-style discussion about entrepreneurship"
- "Storytelling podcast about urban legends"

## 🛠️ Technical Details

### Architecture
- **Frontend**: HTML5, CSS3 (Tailwind CSS), Vanilla JavaScript
- **Backend**: Python Flask with real AI API integrations
- **AI Services**: 
  - OpenRouter (text generation)
  - ElevenLabs (audio synthesis)
  - Stability AI (image generation)
  - Replicate (video generation)
- **Styling**: Modern gradient design with responsive layout

### Working AI APIs Integrated

#### 🎵 Music Generation
- **Text Generation**: OpenRouter API for song composition, lyrics, and musical arrangements
- **Audio Synthesis**: ElevenLabs API for converting text descriptions to audio
- **Features**: Genre selection, mood customization, duration control

#### 🎬 Video Generation  
- **Image Generation**: Stability AI for creating video preview frames
- **Video Processing**: Replicate API for video generation (with fallback to image previews)
- **Features**: Multiple visual styles, duration control, cinematic descriptions

#### 🎨 Cover Art Generation
- **Image Generation**: Stability AI SDXL model for high-quality artwork
- **Features**: Multiple art styles, professional layouts, custom titles
- **Output**: 1024x1024 PNG images

#### 📚 Story Generation
- **Text Generation**: OpenRouter API with specialized creative writing prompts
- **Features**: Multiple genres, length control, file downloads
- **Output**: Complete stories with automatic title extraction

#### 🎙️ Podcast Generation
- **Script Generation**: OpenRouter API for podcast content creation
- **Audio Synthesis**: ElevenLabs API for realistic voice generation
- **Features**: Multiple formats, voice styles, transcript generation

### API Endpoints
- `POST /api/generate-music` - Music generation with real audio output
- `POST /api/generate-video` - Video generation with image previews
- `POST /api/generate-cover` - Cover art generation with Stability AI
- `POST /api/generate-story` - Story generation with file downloads
- `POST /api/generate-podcast` - Podcast generation with audio synthesis
- `GET /api/status` - System status and API availability
- `GET /api/voices` - Available ElevenLabs voices
- `GET /api/models` - Available AI models
- `GET /generated/<filename>` - Serve generated content files

### File Structure
```
pancha-charcha/
├── index.html          # Main application interface
├── js/
│   └── app.js         # Frontend JavaScript logic
├── server.py          # Flask backend server
├── requirements.txt   # Python dependencies
├── .env.local        # Environment configuration
├── start.sh          # Startup script
└── README.md         # This file
```

## 🔒 Security & Privacy

- API keys are stored securely in environment variables
- No user data is permanently stored on the server
- All AI processing is handled through secure OpenRouter API
- Generated content is temporarily cached for download purposes only

## 🐛 Troubleshooting

### Common Issues

**"OpenRouter API key not configured"**
- Ensure your API key is correctly set in `.env.local`
- Verify the API key is valid at [openrouter.ai](https://openrouter.ai)

**"Module not found" errors**
- Run `pip install -r requirements.txt` to install dependencies
- Ensure you're using Python 3.8 or higher

**Server won't start**
- Check if port 8000 is already in use
- Try changing the PORT in `.env.local` to a different value

**AI generation fails**
- Verify your OpenRouter API key has sufficient credits
- Check your internet connection
- Try with a simpler prompt

### Getting Help

If you encounter issues:
1. Check the browser console for JavaScript errors
2. Review the server logs in your terminal
3. Verify all environment variables are correctly set
4. Ensure all dependencies are installed

## 🚀 Deployment

### Local Development
The application is configured for local development by default.

### Production Deployment
For production deployment:
1. Set `FLASK_ENV=production` in your environment
2. Use a production WSGI server like Gunicorn
3. Configure proper security headers and HTTPS
4. Set up proper logging and monitoring

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## 🔮 Future Enhancements

- Real-time collaboration features
- Advanced audio/video processing
- Integration with more AI models
- User accounts and project saving
- Batch processing capabilities
- API rate limiting and usage analytics

---

**Pancha Charcha** - Where creativity meets artificial intelligence! 🎨✨
