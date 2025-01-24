# God of Bacteria 2

A sophisticated tool for analyzing bacterial colony growth in petri dishes, featuring interactive analysis, time series visualization, and detailed statistical analysis. This tool is specifically designed to measure the radius and thickness of ring-like bacterial colonies ("collapsed condom" pattern) in petri dishes.

## Features

- Interactive selection of petri dish regions
- Automated detection of colony radius and ring thickness
- Time series analysis of colony growth
- Detailed visualizations and statistical analysis
- Support for batch processing multiple images

## Requirements

- Python 3.8+
- OpenCV
- NumPy
- Pandas
- Matplotlib
- Seaborn
- SciPy

## Installation

1. Clone the repository:
```bash
git clone https://github.com/patrickliu0077/god-of-bacteria-2.git
cd god-of-bacteria-2
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

## Usage

### Basic Usage

Run the analysis on a sequence of images:
```bash
python src/batch_analyzer.py path/to/image/directory output/directory
```

### Interactive Workflow

1. **Phase 1: Select Petri Dish Regions**
   - The first image will be displayed
   - Click and drag to draw squares around each petri dish
   - Press 'r' to reset if you make a mistake
   - Press 'n' when you've selected all 6 dishes
   - These regions will be used for all subsequent images

2. **Phase 2: Mark Colony Centers**
   - For each dish in each image:
     * Click to set the colony center
     * Press 'r' to reset if needed
     * Press 'n' to move to the next dish
   - The tool will automatically:
     * Detect the colony ring
     * Measure radius and thickness
     * Generate visualizations

3. **Results**
   - The tool will automatically generate:
     * Individual colony measurements
     * Time series analysis
     * Growth curves
     * Statistical summaries

### Output Structure

```
output_directory/
├── measurements.csv       # All individual measurements
├── measurements.json     # Same data in JSON format
├── summary.csv          # Statistics by image
├── visualizations/      # Analysis visualizations
│   └── [image_name]/
│       ├── dish_1_analysis.png
│       ├── dish_1_profile.png
│       └── dish_1_gradient.png
└── time_series/        # Time series analysis
    ├── growth_curves.png
    ├── growth_rates.png
    ├── dish_comparisons.png
    ├── correlation_matrix.png
    ├── time_series_stats.csv
    └── dish_stats.csv
```

### Understanding Visualizations

1. **Colony Analysis (dish_X_analysis.png)**
   - Original image with measurements overlay
   - Green circle: Outer edge of colony
   - Blue circle: Inner edge of ring
   - Red dot: Colony center
   - Measurements in pixels

2. **Radial Profile (dish_X_profile.png)**
   - Shows intensity variation from center to edge
   - Helps verify edge detection accuracy

3. **Growth Curves (growth_curves.png)**
   - Radius and thickness over time
   - Each line represents one dish

4. **Growth Rates (growth_rates.png)**
   - Change in radius and thickness over time
   - Shows growth dynamics

5. **Dish Comparisons (dish_comparisons.png)**
   - Comparative analysis between dishes
   - Includes statistical distributions

### Tips for Best Results

1. **Image Quality**
   - Ensure good lighting and contrast
   - Minimize reflections and shadows
   - Keep camera position consistent between images

2. **Region Selection**
   - Make squares slightly larger than dishes
   - Keep consistent orientation for all dishes

3. **Center Selection**
   - Click as close to the true center as possible
   - Use visual guides (ring pattern) to help

## Example Workflow

1. Prepare your images in a directory:
```
images/
├── t001.jpg
├── t002.jpg
└── t003.jpg
```

2. Run the analysis:
```bash
python src/batch_analyzer.py images output
```

3. Follow the interactive prompts to:
   - Select dish regions in first image
   - Mark colony centers in each image

4. Review the results in the output directory:
   - Check visualizations for accuracy
   - Analyze growth curves
   - Review statistical summaries

## Troubleshooting

- If colony detection fails, try adjusting lighting conditions
- If regions are misaligned, use 'r' to reset and redraw
- For any issues, check the logs in output/logs/

## License

MIT License

## Contact

Patrick Liu - patrickliu0077@gmail.com

Project Link: [https://github.com/patrickliu0077/god-of-bacteria-2](https://github.com/patrickliu0077/god-of-bacteria-2)
