# Video Subtitles Detector Program

The Video Subtitles Detector Program is designed to process a video frame by frame, segmenting words and subtitles, and detecting another area of interest. The program first converts each frame to grayscale and applies adaptive thresholding to create a binary mask highlighting text regions.

For segmenting words, the program analyzes the upper portion of the frame, where subtitles are typically located, and uses morphological operations to connect text regions. It then finds contours within this region and creates bounding boxes for each word, drawing them in green.

To detect subtitles, the program focuses on the lower portion of the frame and extracts the region of interest. It then follows a similar process of finding contours and creating bounding boxes, this time drawing them in red. If subtitles span multiple lines, the program merges overlapping bounding boxes into single bounding boxes for each line.

Finally, the program also detects another area of interest within the frame using similar techniques and draws bounding boxes around the detected regions.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/KareemMoneeam/video-subtitles-detector.git
   ```

2. Install dependencies:
   ```bash
   pip install opencv-python matplotlib numpy
   ```

## Usage

1. **Input**: Provide a video file with subtitles.
2. **Output**: The program will output the same video with bounding boxes drawn around subtitles, words, and the other area of interest.

3. **Running the program**:
   ```bash
   python video_subtitles_detector.py --video_path path_to_your_video
   ```

## Implementation

The program uses the following techniques:
- Conversion to grayscale and adaptive thresholding for text region detection.
- Morphological operations to connect text regions.
- Contour detection and bounding box creation for words and subtitles.
- Merging overlapping bounding boxes for subtitles spanning multiple lines.
- Drawing bounding boxes in green for words, and in red for subtitles.

## Dependencies

- OpenCV: `pip install opencv-python`
- Matplotlib: `pip install matplotlib`
- NumPy: `pip install numpy`
