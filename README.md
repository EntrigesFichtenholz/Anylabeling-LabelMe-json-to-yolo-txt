# Anylabeling-LabelMe-json-to-yolo-txt
Python scripts for converting .json annotations from [Anylabeling](https://github.com/vietanhdev/anylabeling) or [LabelMe](https://github.com/wkentaro/labelme) to YOLO .txt files.

-**jsontoyolo.py** will convert the .json annotation files to YOLO .txt files, split them into 'train' and 'validate' folders and copy over the corresponding pictures. 
Tracks progress using a progress bar. Requires *scikit-learn* and *tqdm*.

-**jsontoyolo_simple.py** will only convert the .json files to YOLO .txt files and copy them to your specified directory. Only uses built-in Python modules.

**Usage:**
Configuration Setup
    *Hardcodet*
    Set input_dir to the directory where your original dataset resides, and output_dir where you want to save the converted YOLO files.

Specify Train-Validation Split Ratio
    *Hardcodet*
    Adjust the split_ratio to control how much data is allocated for validation (e.g., 0.2 for 20%). The script will ask you whether to apply a split.
    
    Run the script. You will be prompted: Would you like to split the dataset into training and validation sets? (yes/no). Choose yes to use the specified split ratio or no to keep all         data for training.

File Extensions
    
    By default, the script handles images with extensions .jpg, .png, and .jpeg. If your dataset includes other extensions, you will need to modify lines in the script that filter for          specific image formats.

Output

    Each JSON file is converted to a YOLO-compatible .txt file with bounding box data normalized to the range [0, 1], based on each image’s width and height.

Logging

    Logging outputs are saved to dataset_conversion.log and displayed in the console. Key information includes:
        Total JSON and image files detected in input_dir
        Automatic discovery of unique labels
        Conversion progress and error messages

---

