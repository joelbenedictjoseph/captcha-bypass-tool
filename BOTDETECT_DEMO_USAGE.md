# BotDetect CAPTCHA Demo Bypass Usage Guide

## Overview
This guide explains how to use the BotDetect CAPTCHA demo bypass feature in the captcha bypass script.

## Supported Website
- **BotDetect CAPTCHA Demo**: https://captcha.com/demos/features/captcha-demo.aspx

## Prerequisites
1. Ensure you have all required dependencies installed:
   ```bash
   pip install -r requirements.txt
   ```

2. Set up your `.env` file with the required API keys:
   ```
   GEMINI_API_KEY=your_gemini_api_key_here
   ```

## How to Run
Execute the following command in your terminal:
```bash
python main.py botdetect_demo
```

## What the Script Does
1. **Navigation**: Opens the BotDetect CAPTCHA demo page
2. **Full Page Screenshot**: Saves a screenshot of the entire page for debugging
3. **CAPTCHA Detection**: Locates the CAPTCHA image using multiple selector strategies:
   - XPath: `//img[contains(@id, 'CaptchaImage')]`
   - CSS Selector: `img[id*='CaptchaImage']`
   - Tag Name: `img` (fallback)
4. **Image Capture**: Takes a screenshot of the CAPTCHA image
5. **AI Processing**: Uses Gemini AI to analyze and solve the CAPTCHA
6. **Input**: Enters the solution into the text input field
7. **Submission**: Clicks the validate button or presses Enter as fallback
8. **Result**: Saves a screenshot of the result page

## Generated Files
After running the script, you'll find these files in your directory:
- `botdetect_full_page.png` - Full page screenshot for debugging
- `botdetect_captcha.png` - Individual CAPTCHA image
- `botdetect_result.png` - Result page after submission

## Features
- **Robust Element Detection**: Uses multiple selector strategies with fallbacks
- **AI-Powered CAPTCHA Solving**: Leverages Gemini AI for text recognition
- **Enhanced Debugging**: Provides screenshots at each step
- **Error Handling**: Graceful fallbacks when elements aren't found
- **Multiple Submission Methods**: Tries button click first, then Enter key

## Troubleshooting
- If the script fails to find elements, check the generated screenshots
- Ensure your Gemini API key is correctly set in the `.env` file
- The script includes multiple fallback strategies for element detection
- Check the console output for detailed step-by-step information

## Success Indicators
Look for these messages in the console output:
- "Found captcha image using [selector type]"
- "Captcha solution: [extracted text]"
- "Entered captcha solution: [text]"
- "Found validate button using [selector type]"
- "Clicked validate button"
- "Result screenshot saved as 'botdetect_result.png'"

## Notes
- The script uses Firefox WebDriver by default
- CAPTCHA solving accuracy depends on image quality and AI model performance
- The script includes a 3-second wait after submission for the page to load