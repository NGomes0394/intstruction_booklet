# Meal Prep Instruction Booklet Generator

A Python script that generates a formatted, multi-page PDF instruction booklet from recipe notes and photos. Built for sharing meal prep instructions with caregivers.

## Requirements

- Python 3.7+
- [ReportLab](https://pypi.org/project/reportlab/) — PDF generation
- [Pillow](https://pypi.org/project/Pillow/) — image processing and EXIF handling

Install both with:

```bash
pip install reportlab Pillow
```

## Setup

### 1. Folder Structure

Organize your files like this:

```
your_folder/
├── instruction_booklet.py
└── images/
    ├── IMG_0285.jpeg
    ├── IMG_0289.jpeg
    └── ... (all referenced photos)
```

### 2. Update the Paths

Open `instruction_booklet.py` and update these two lines near the top to match your machine:

```python
OUTPUT_PDF = "/path/to/output/Instruction_Booklet.pdf"  # where the PDF will be saved
IMG_DIR = "/path/to/your/images"                        # folder containing your photos
```

**Example (Mac):**
```python
OUTPUT_PDF = "/Users/yourname/Desktop/Instruction_Booklet.pdf"
IMG_DIR = "/Users/yourname/Desktop/images"
```

## Usage

Once paths are set and dependencies are installed, run:

```bash
python instruction_booklet.py
```

The PDF will be saved to the location you set in `OUTPUT_PDF`.

## What's in the PDF

The generated booklet includes:

| Page | Content |
|------|---------|
| 1 | Cover page |
| 2 | Table of contents |
| 3 | General meal guidelines & lunch packing photos |
| 4 | Morning smoothie recipe |
| 5–6 | Waffles with peanut butter & syrup |
| 7–8 | Chicken nuggets |
| 9 | Peanut butter & jelly toast |
| 10 | Ramen, french toast sticks, turkey hotdogs |
| 11 | Isabelle's food preferences |

## Required Images

The script expects the following image files in your `IMG_DIR` folder:

| File | Used For |
|------|---------|
| `IMG_0285.jpeg` | Waffles – ingredients |
| `IMG_0289.jpeg` | Waffles – toasted |
| `IMG_0290.jpeg` | Waffles – peanut butter spread |
| `IMG_0291.jpeg` | Waffles – cut & drizzled |
| `IMG_0308.jpeg` | Nuggets – ketchup & serving plate |
| `IMG_0310.jpeg` | Nuggets – air fryer set |
| `IMG_0311.jpeg` | Nuggets – cooked |
| `IMG_0312.jpeg` | Nuggets – cut into pieces |
| `IMG_0317.jpeg` | Nuggets – served with ketchup |
| `IMG_0346.jpeg` | PB&J toast – finished result |
| `IMG_0367.jpeg` | Lunch packing reference 1 |
| `IMG_0371.jpeg` | Lunch packing reference 2 |
| `IMG_0373.jpeg` | Lunch packing reference 3 |
| `IMG_0375.jpeg` | Smoothie – ingredients |
| `IMG_0376.jpeg` | Smoothie – blended & ready |

> Missing images won't crash the script — they'll just be skipped with an error printed to the console.

## Customization

- **Colors** — Blue theme is used for Juliette's recipes, pink for Isabelle's. Both color palettes are defined at the top of the file and can be changed by updating the `HexColor` values.
- **Recipes** — Each recipe section is self-contained and can be edited, removed, or duplicated for new recipes.
- **Page size** — Defaults to US Letter. Change `from reportlab.lib.pagesizes import letter` and the `pagesize` argument to use A4 or another size.
