Automatic Number Plate Recognition (ANPR) with YOLOv8
This project implements a high-performance Automatic Number Plate Recognition (ANPR) system using YOLOv8 for object detection, SORT for vehicle tracking, and EasyOCR for text extraction. It is designed to process traffic footage, identify individual vehicles, and log their license plate numbers into a structured format.

🚀 Key Features
Vehicle Detection & Tracking: Uses YOLOv8 and SORT to maintain unique identities for vehicles across video frames.

License Plate Recognition: A specialized YOLOv8 model trained specifically to detect license plates in various conditions.

OCR Post-Processing: Automated character mapping (e.g., 'O' to '0', 'I' to '1') to improve recognition accuracy for standard license formats.

Data Interpolation: A custom script to fill in missing detection gaps using linear interpolation, ensuring smooth data logs even if a frame is missed.

Visualization: Generates an output video with overlaid bounding boxes and real-time OCR results.

🛠️ Installation
1. Clone the Repository
Bash
git clone <your-repository-url>
cd automatic-number-plate-recognition-python-yolov8
2. Install Dependencies
Ensure you have Python installed, then run:

Bash
pip install -r requirements.txt
Note: This project requires ultralytics, opencv-python, easyocr, and scipy.

3. Setup SORT Tracker
The SORT module must be downloaded separately. Clone it into your project directory:

Bash
git clone https://github.com/abewley/sort.git
📂 Project Structure
main.py: The core execution script for detection and OCR.

util.py: Contains helper functions for OCR formatting and CSV writing.

add_missing_data.py: Refines the output data by interpolating missing frames.

visualize.py: Creates the final video output with visual annotations.

🚦 Usage
Run the Detection:
Place your input video as sample.mp4 and run:

Bash
python main.py
This generates test.csv containing raw detection results.

Interpolate Missing Data:
Refine the CSV to fill in gaps in tracking:

Bash
python add_missing_data.py
Generate Visualization:
Create the final annotated video:

Bash
python visualize.py
⚖️ License
This project is licensed under the GNU Affero General Public License v3.0 (AGPL-3.0). This means that if you run a modified version of this software over a network, you must provide the source code of your modifications to your users.

🙏 Credits
YOLOv8 by Ultralytics.

SORT by abewley.

EasyOCR by JaidedAI.
