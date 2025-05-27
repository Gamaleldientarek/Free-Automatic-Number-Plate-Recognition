# Automatic Number Plate Recognition (ANPR) with YOLO11

A comprehensive implementation of Automatic Number Plate Recognition using Ultralytics YOLO11 and EasyOCR for accurate license plate detection and text extraction.

## 🚗 Features

- **Real-time License Plate Detection**: Uses YOLO11 for precise plate localization
- **Text Recognition**: EasyOCR integration for accurate text extraction
- **Video Processing**: Process entire video files frame by frame
- **Image Processing**: Single image analysis capability
- **Free Alternative**: Uses EasyOCR instead of paid APIs like OpenAI

## 📋 Requirements

```bash
pip install ultralytics
pip install easyocr==1.7.1
pip install opencv-python
pip install numpy
pip install matplotlib
```

## 🚀 Quick Start

### For Video Processing

```python
import cv2
import easyocr
from ultralytics import YOLO
from ultralytics.utils.plotting import Annotator, colors

# Initialize EasyOCR Reader
reader = easyocr.Reader(['en'])

# Load the YOLO model
model = YOLO("anpr-demo-model.pt")  # Download from releases

# Process video
cap = cv2.VideoCapture("your_video.mp4")
# ... (see notebook for full implementation)
```

### For Single Image Processing

```python
# Read image
im0 = cv2.imread("your_image.jpg")

# Initialize model and OCR
model = YOLO("anpr-demo-model.pt")
reader = easyocr.Reader(['en'])

# Process image
results = model.predict(im0)[0].boxes
# ... (see notebook for full implementation)
```

## 📁 Project Structure

```
anpr-yolo11-project/
├── Free_Automatic_Number_Plate_Recognition.ipynb
├── src/
│   ├── anpr_processor.py
│   └── utils.py
├── models/
│   └── anpr-demo-model.pt (download from releases)
├── examples/
│   ├── sample_images/
│   └── sample_videos/
├── requirements.txt
├── README.md
└── LICENSE
```

## 🎯 How It Works

1. **Detection**: YOLO11 identifies license plate regions in images/video frames
2. **Preprocessing**: Crops detected regions with padding for better OCR accuracy  
3. **Text Extraction**: EasyOCR processes cropped regions to extract text
4. **Annotation**: Results are overlaid on original images with bounding boxes and text

## 📊 Performance

- **Accuracy**: High precision in various lighting conditions
- **Speed**: Real-time processing capability
- **Robustness**: Works with different plate formats and angles

## 🔧 Configuration

### Padding Settings
```python
padding = 10  # Adjust based on your needs
```

### Supported Languages
```python
reader = easyocr.Reader(['en', 'es', 'fr'])  # Add more languages as needed
```

## 📝 Usage Examples

### Process Video File
```bash
python src/anpr_processor.py --input video.mp4 --output result.avi
```

### Process Single Image
```bash
python src/anpr_processor.py --input image.jpg --output annotated_image.jpg
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Ultralytics](https://ultralytics.com/) for the YOLO11 model
- [EasyOCR](https://github.com/JaidedAI/EasyOCR) for text recognition
- Original notebook inspiration from Ultralytics community

## 📞 Support

If you have any questions or issues, please:
1. Check the [Issues](../../issues) section
2. Create a new issue if your problem isn't already reported
3. Provide detailed information about your setup and the issue

## 🔗 Links

- [YOLO11 Documentation](https://docs.ultralytics.com/)
- [EasyOCR Documentation](https://github.com/JaidedAI/EasyOCR)
- [Demo Video](link-to-demo-video)

---

⭐ **Star this repository if you found it helpful!**
