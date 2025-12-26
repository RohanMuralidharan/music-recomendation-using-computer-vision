# 🎵 Emotion-Based Music Recommendation System

An intelligent music recommendation system that uses real-time emotion detection through facial expressions and hand gestures to suggest personalized music. Built with deep learning, computer vision, and web technologies.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Importance & Applications](#importance--applications)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Usage Guide](#usage-guide)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Project Overview

This project combines **Computer Vision**, **Deep Learning**, and **Web Development** to create an interactive music recommendation system. The application:

1. **Captures** real-time video feed from your webcam
2. **Analyzes** facial expressions and hand gestures using MediaPipe
3. **Detects** emotions using a pre-trained Keras neural network model
4. **Recommends** music by opening YouTube search results based on detected emotion, language, and artist preferences

### Explanation Video
[![Watch the Video](emotion.jpg)](https://youtu.be/uDzLxos0lNU)

**Video Link:** [Emotion based music | ai | deep learning project | with code | ml project](https://youtu.be/uDzLxos0lNU)

## 🌟 Importance & Applications

### Why This Project Matters:

1. **Personalized User Experience**: Provides music recommendations based on real-time emotional state rather than just listening history
2. **Mental Health Applications**: Can be used in therapeutic settings to suggest mood-appropriate music
3. **Entertainment Industry**: Demonstrates how AI can enhance user engagement in music streaming platforms
4. **Educational Value**: Showcases integration of multiple technologies (CV, ML, Web Dev)
5. **Real-time Processing**: Demonstrates efficient real-time emotion detection using modern frameworks

### Real-World Applications:

- Music streaming platforms (Spotify, YouTube Music, etc.)
- Mental health and wellness apps
- Smart home systems with mood-based automation
- Interactive kiosks and entertainment systems
- Research in affective computing

## 🛠️ Tech Stack

### Core Technologies

- **Python 3.9.7** - Programming language
- **Streamlit 1.12.0** - Web application framework
- **Streamlit-WebRTC** - Real-time webcam streaming in browser
- **MediaPipe 0.10.14** - Face and hand landmark detection
- **OpenCV** - Computer vision and image processing
- **Keras/TensorFlow** - Deep learning model for emotion classification
- **NumPy** - Numerical computations

### Libraries & Dependencies

- **av (PyAV)** - Video frame processing
- **webbrowser** - Opening YouTube search results
- **protobuf 4.25.8** - Protocol buffers (with compatibility workaround)

## ✨ Features

- ✅ Real-time emotion detection from facial expressions
- ✅ Hand gesture recognition for enhanced emotion analysis
- ✅ Live webcam feed processing in the browser
- ✅ Pre-trained deep learning model for emotion classification
- ✅ Personalized music recommendations via YouTube
- ✅ Multi-language support
- ✅ Artist-specific recommendations
- ✅ Interactive web interface

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

1. **Python 3.9.7** (Important: Python 3.9.7 specifically, as newer Streamlit versions don't support it)
   - Download from [python.org](https://www.python.org/downloads/)
   - Verify installation: `python --version`

2. **Webcam** - Required for emotion detection

3. **Internet Connection** - For YouTube music recommendations

4. **Git** (optional) - For cloning the repository

## 🚀 Installation

### Step 1: Clone or Download the Repository

```bash
git clone <repository-url>
cd Music-recomendation-system-based-on-emotion-main
```

Or download and extract the ZIP file.

### Step 2: Create a Virtual Environment (Recommended)

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies

**Important:** Due to compatibility issues between different package versions, install packages in the following order:

```bash
# Install core packages first
python -m pip install --upgrade pip

# Install streamlit (version 1.12.0 for Python 3.9.7 compatibility)
python -m pip install streamlit==1.12.0

# Install altair (compatible version)
python -m pip install "altair>=4.0,<5.0"

# Install mediapipe (version 0.10.14 has the old solutions API)
python -m pip install --user mediapipe==0.10.14

# Install protobuf (required by mediapipe, with compatibility workaround)
python -m pip install protobuf==4.25.8

# Install remaining dependencies
python -m pip install opencv-python opencv-contrib-python numpy keras tensorflow streamlit-webrtc av
```

### Step 4: Verify Installation

```bash
# Test if all packages are installed correctly
python -c "import streamlit; import cv2; import mediapipe; import numpy; import keras; print('All packages installed successfully!')"
```

## 🏃 Running the Application

### Method 1: Direct Run (Recommended)

```bash
python -m streamlit run music.py
```

### Method 2: Using Streamlit Command

```bash
streamlit run music.py
```

### Access the Application

Once the server starts, you'll see output like:

```
You can now view your Streamlit app in your browser.

Local URL: http://localhost:8501
Network URL: http://192.168.x.x:8501
```

Open your web browser and navigate to `http://localhost:8501`

## 📖 Usage Guide

### Step-by-Step Instructions:

1. **Launch the Application**
   - Run `python -m streamlit run music.py`
   - Open the browser URL shown in the terminal

2. **Enter Preferences**
   - **Language**: Enter your preferred language (e.g., "English", "Hindi", "Spanish")
   - **Singer**: Enter your favorite artist name (e.g., "Taylor Swift", "Arijit Singh")

3. **Allow Camera Access**
   - When prompted, click "Allow" to grant camera permissions
   - The webcam feed will appear in the browser

4. **Show Your Emotion**
   - Position yourself in front of the camera
   - Make facial expressions and hand gestures
   - The detected emotion will appear on the video feed
   - Wait for the emotion to be captured (it will be saved automatically)

5. **Get Recommendations**
   - Click the "Recommend me songs" button
   - A new browser tab will open with YouTube search results
   - Results will be based on: `[Language] + [Detected Emotion] + song + [Singer]`

### Example Usage:

- **Language**: "English"
- **Singer**: "Ed Sheeran"
- **Detected Emotion**: "Happy"
- **Result**: Opens YouTube search for "English Happy song Ed Sheeran"

## 📁 Project Structure

```
Music-recomendation-system-based-on-emotion-main/
│
├── music.py                 # Main application file
├── model.h5                 # Pre-trained Keras emotion detection model
├── labels.npy               # Emotion labels array
├── emotion.npy              # Current detected emotion (generated at runtime)
├── emotion.jpg              # Project thumbnail/image
├── requirements.txt         # Python dependencies
├── README.md                # This file
└── .gitignore               # Git ignore file
```

### File Descriptions:

- **music.py**: Main Streamlit application with emotion detection logic
- **model.h5**: Pre-trained neural network model for emotion classification
- **labels.npy**: Array containing emotion label names
- **emotion.npy**: Stores the currently detected emotion (created at runtime)

## 🔧 Troubleshooting

### Issue 1: `ModuleNotFoundError: No module named 'mediapipe'`

**Solution:**
```bash
python -m pip install --user mediapipe==0.10.14
```

### Issue 2: `AttributeError: module 'mediapipe' has no attribute 'solutions'`

**Solution:** This happens with newer MediaPipe versions. Install the older version:
```bash
python -m pip uninstall mediapipe
python -m pip install --user mediapipe==0.10.14
```

### Issue 3: `TypeError: Descriptors cannot be created directly` (Protobuf Error)

**Solution:** The code already includes a workaround. If you still see this error:
```bash
# Ensure protobuf version is correct
python -m pip install protobuf==4.25.8
```

The `music.py` file already sets the environment variable at the start to handle this.

### Issue 4: `ModuleNotFoundError: No module named 'altair.vegalite.v4'`

**Solution:**
```bash
python -m pip install "altair>=4.0,<5.0"
```

### Issue 5: Streamlit version compatibility issues

**Solution:** For Python 3.9.7, use Streamlit 1.12.0:
```bash
python -m pip install streamlit==1.12.0
```

### Issue 6: Camera not working

**Solutions:**
- Check if another application is using the camera
- Grant camera permissions in your browser
- Try refreshing the page
- Check if your webcam is properly connected

### Issue 7: Model file not found

**Ensure these files are in the project directory:**
- `model.h5`
- `labels.npy`

If missing, download them from the repository.

### Issue 8: Slow performance

**Tips:**
- Close other applications using the camera
- Ensure good lighting for better face detection
- Close unnecessary browser tabs
- Check your internet connection

## 🔍 Technical Details

### How It Works:

1. **Video Capture**: Streamlit-WebRTC captures video frames from the webcam
2. **Landmark Detection**: MediaPipe detects face and hand landmarks
3. **Feature Extraction**: Coordinates are extracted and normalized
4. **Emotion Classification**: Pre-trained Keras model predicts emotion
5. **Music Recommendation**: YouTube search is opened with emotion + preferences

### Model Architecture:

- Uses a pre-trained Keras model (`model.h5`)
- Input: Normalized landmark coordinates (face + hands)
- Output: Emotion classification (Happy, Sad, Angry, etc.)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 Notes

- **Python Version**: This project is tested with Python 3.9.7. Other versions may have compatibility issues.
- **Camera Required**: A working webcam is essential for the application to function.
- **Browser Compatibility**: Works best with Chrome, Firefox, or Edge browsers.
- **Performance**: Emotion detection works best with good lighting and clear face visibility.

## 📚 Additional Resources

- [MediaPipe Documentation](https://mediapipe.dev/)
- [Streamlit Documentation](https://docs.streamlit.io/)
- [Keras Documentation](https://keras.io/)
- [OpenCV Documentation](https://opencv.org/)

## 👨‍💻 Author

Original project by [Pawandeep-prog](https://github.com/Pawandeep-prog)

### Connect with the Creator:
- **Facebook**: [programminghub](https://m.facebook.com/proogramminghub)
- **Instagram**: [@programming_hut](https://instagram.com/programming_hut)
- **Twitter**: [@programming_hut](https://twitter.com/programming_hut)
- **GitHub**: [Pawandeep-prog](https://github.com/Pawandeep-prog)
- **Discord**: [Join Server](https://discord.gg/G5Cunyg)
- **LinkedIn**: [programminghut](https://www.linkedin.com/in/programminghut)
- **YouTube**: [programminghutofficial](https://www.youtube.com/c/programminghutofficial)

## 📄 License

This project is open source and available for educational purposes.

## 🙏 Acknowledgments

- MediaPipe team for the excellent computer vision framework
- Streamlit team for the amazing web framework
- All contributors and users of this project

---

**Made with ❤️ using Python, Deep Learning, and Computer Vision**

For any queries or issues, please open an issue on the repository or contact the author through the links above.
