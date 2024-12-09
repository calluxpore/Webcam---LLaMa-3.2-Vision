# Webcam-LLaMA 3.2 Vision

This project captures images from your webcam, processes them using the LLaMA 3.2 Vision model, and generates detailed, structured analyses based on Kim Vicente's Human Organizational Ladder. The application logs descriptions in a text file and provides immediate feedback in the console.

---

## Features

- **Webcam Integration**: Captures high-resolution (1080p) images from the webcam.
- **LLaMA 3.2 Vision**: Sends images for advanced multimodal analysis, including dimensions like physical, psychological, team, organizational, and political aspects.
- **Detailed Analysis**: Generates expert-level image descriptions and insights.
- **Logging**: Logs analyses with timestamps in a text file (`llama_output.txt`).

---

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/webcam-llama3.2-vision.git
   cd webcam-llama3.2-vision
   ```

2. **Install Python Dependencies**:
   ```bash
   pip install opencv-python requests
   ```

3. **Set Up LLaMA 3.2 Vision**:
   - Ensure the LLaMA 3.2 Vision model is installed and the API is running locally.
   - Start the server:
     ```bash
     llama serve
     ```
   - Pull the Vision model:
     ```bash
     llama pull llama3.2-vision
     ```

---

## Running the Application

1. **Start the Application**:
   ```bash
   python webcam_llama3.2.py
   ```

2. **Automatic Image Analysis**:
   - The application captures an image every 20 seconds, analyzes it, and logs the description in `llama_output.txt`.

3. **Stop the Application**:
   - Use `Ctrl + C` in the terminal to stop the process.

---

## Requirements

- **Python 3.x**
- **Python Libraries**:
  - OpenCV
  - Requests
- **LLaMA 3.2 Vision**:
  - Ensure the model and server are correctly set up locally.

Install the dependencies with:
```bash
pip install opencv-python requests
```

---

## How It Works

1. **Image Capture**:
   - Opens the webcam and captures an image.
   - Saves the image locally with a timestamp.

2. **Base64 Conversion**:
   - Converts the image to a base64 format for compatibility with the API.

3. **API Interaction**:
   - Sends the base64 image and a detailed prompt to the LLaMA 3.2 Vision API.
   - Receives structured, multidimensional analysis.

4. **Logging**:
   - Logs the analysis results in `llama_output.txt` with timestamps.

---

## Example Prompt

The application uses a detailed prompt for structured analysis:
> You are an expert image investigator tasked with conducting a structured analysis using Kim Vicente’s Human Organizational Ladder. Begin with an overall analysis of the scene, describing the setting, objects, colors, people, and notable details. Then, systematically examine the image through the Physical (size, shape, material), Psychological (information flow, cause-effect), Team (authority, communication, responsibilities), Organizational (culture, structures), and Political (laws, policies, regulations) dimensions. Conclude with critical insights, highlighting significant observations, questions, and areas for deeper exploration—ensuring no section is omitted for a complete analysis.

---

## Troubleshooting

- **Webcam Issues**:
  - Ensure the webcam is not in use by another application.
  - For Windows, use `cv2.CAP_DSHOW`; switch to `cv2.CAP_MSMF` if needed.

- **API Errors**:
  - Confirm the LLaMA 3.2 Vision API is running on `localhost:11434`.
  - Verify the model is correctly pulled and initialized.

- **Invalid JSON Response**:
  - Check the API response for errors.
  - Ensure the image size and format meet the model's requirements.

---

## Acknowledgements

- **OpenCV**: Used for webcam handling and image capture.
- **LLaMA 3.2 Vision**: Provides advanced multimodal analysis.
- **Kim Vicente's Human Organizational Ladder**: Framework for structured image analysis.