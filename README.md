# CAPTCHA Bypass Tool

A comprehensive Python-based tool for bypassing various types of CAPTCHAs using AI-powered image recognition and automated web interaction. This tool supports multiple CAPTCHA types including reCAPTCHA, text-based CAPTCHAs, puzzle CAPTCHAs, and more.

## 🚀 Features

- **Multiple CAPTCHA Types Support**:
  - reCAPTCHA (image-based challenges)
  - Text-based CAPTCHAs
  - Complicated text CAPTCHAs
  - Puzzle/Slider CAPTCHAs
  - BotDetect demo CAPTCHAs
  - 2captcha text challenges

- **AI-Powered Recognition**:
  - Google Gemini AI integration for advanced image analysis
  - Specialized prompts for different CAPTCHA types
  - High accuracy text and image recognition

- **Robust Automation**:
  - Selenium WebDriver for browser automation
  - Multiple selector strategies with fallbacks
  - Comprehensive error handling
  - Screenshot capture for debugging

- **Cross-Platform Support**:
  - Works on Windows, macOS, and Linux
  - Firefox WebDriver with automatic driver management

## 📋 Prerequisites

- Python 3.7 or higher
- Firefox browser installed
- Google Gemini API key

## 🛠️ Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd captcha-bypass
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**:
   - Copy `.env.example` to `.env`:
     ```bash
     cp .env.example .env
     ```
   - Edit `.env` and add your Google Gemini API key:
     ```
     GEMINI_API_KEY=your_gemini_api_key_here
     ```

## 🎯 Usage

The tool supports various CAPTCHA types through command-line arguments:

```bash
python main.py <captcha_type>
```

### Supported CAPTCHA Types:

#### 1. reCAPTCHA
```bash
python main.py recaptcha
```
Solves Google reCAPTCHA challenges with image recognition (cars, traffic lights, crosswalks, etc.)

#### 2. Text CAPTCHA
```bash
python main.py text
```
Solves simple text-based CAPTCHAs with character recognition.

#### 3. Complicated Text CAPTCHA
```bash
python main.py complicated_text
```
Handles complex text CAPTCHAs with distorted or stylized characters.

#### 4. Puzzle/Slider CAPTCHA
```bash
python main.py puzzle
```
Solves slider puzzles and drag-and-drop CAPTCHAs.

#### 5. BotDetect Demo CAPTCHA
```bash
python main.py botdetect_demo
```
Solves BotDetect CAPTCHA demo challenges.
- **Target**: https://captcha.com/demos/features/captcha-demo.aspx

#### 6. 2captcha Text CAPTCHA
```bash
python main.py twocaptcha_text
```
Handles 2captcha service text-based challenges.

## 📁 Generated Files

The tool generates several files during execution for debugging and verification:

- `<captcha_type>_full_page.png` - Full page screenshot
- `<captcha_type>_captcha.png` - CAPTCHA image screenshot
- `<captcha_type>_result.png` - Result page screenshot

## 🔧 Configuration

### Environment Variables

- `GEMINI_API_KEY`: Your Google Gemini API key (required)

### Getting a Gemini API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Create a new API key
4. Copy the key to your `.env` file

## 📦 Dependencies

Key dependencies include:

- `selenium` - Web browser automation
- `google-generativeai` - Google Gemini AI integration
- `Pillow` - Image processing
- `requests` - HTTP requests
- `python-dotenv` - Environment variable management
- `webdriver-manager` - Automatic WebDriver management

See `requirements.txt` for the complete list.

## 🏗️ Architecture

The tool is structured with modular functions for different CAPTCHA types:

- **AI Integration**: Specialized functions for different AI prompts
  - `ask_recaptcha_to_chatgpt()` - reCAPTCHA analysis
  - `ask_text_to_chatgpt()` - Text CAPTCHA analysis
  - `ask_slide_to_chatgpt()` - Puzzle CAPTCHA analysis

- **Test Functions**: Individual test implementations
  - `recaptcha_test()` - reCAPTCHA solving
  - `text_test()` - Text CAPTCHA solving
  - `puzzle_test()` - Puzzle CAPTCHA solving
  - And more...

- **Utility Functions**: Helper functions for common tasks
  - `encode_image_to_base64()` - Image encoding
  - `average_of_array()` - Mathematical calculations

## 🚨 Important Notes

- **Educational Purpose**: This tool is intended for educational and research purposes only
- **Rate Limiting**: Be mindful of API rate limits when using AI services
- **Website Terms**: Respect website terms of service and use responsibly
- **Browser Requirements**: Firefox browser must be installed on the system

## 🐛 Troubleshooting

### Common Issues:

1. **Firefox not found**: Ensure Firefox is installed and accessible
2. **API key errors**: Verify your Gemini API key is correct and active
3. **Element not found**: Websites may change their structure; selectors might need updates
4. **Slow performance**: AI processing can take time; be patient

### Debug Information:

The tool provides comprehensive logging and screenshot capture for debugging:
- Check generated PNG files for visual debugging
- Monitor console output for detailed execution logs
- Verify network connectivity for AI API calls

## 📄 License

This project is for educational purposes. Please use responsibly and in accordance with applicable laws and website terms of service.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

## 📞 Support

For support and questions, please refer to the individual usage guides:
- [BotDetect Demo Usage](BOTDETECT_DEMO_USAGE.md)

---

**Disclaimer**: This tool is provided for educational and research purposes only. Users are responsible for ensuring their use complies with applicable laws and website terms of service.