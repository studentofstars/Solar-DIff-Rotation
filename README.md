# Solar Differential Rotation via Sunspot Tracking

This project uses SunPy, Astropy, NumPy, SciPy, and Matplotlib to track sunspots in solar FITS images, measure their centroid positions, convert pixel coordinates into heliographic coordinates, and estimate solar differential rotation from the change in longitude over time.

The main workflow is implemented in the notebook files in this repository, especially `SunspotTracker.ipynb` and the related analysis notebooks.

## What the project does

- Loads solar FITS images from a local data folder.
- Normalizes each image and isolates a sunspot region using a threshold.
- Computes a weighted centroid for the dark sunspot feature.
- Converts the centroid from pixel coordinates to heliographic coordinates with SunPy.
- Stores the measured longitude and latitude values for later analysis.
- Fits a line to longitude versus time to estimate an apparent rotation rate.


## Requirements

The notebooks were written for a Python environment with the following packages:

- `numpy`
- `scipy`
- `matplotlib`
- `astropy`
- `sunpy`

Depending on your environment, you may also need:

- `jupyter`
- `ipykernel`

## How to run

1. Open the repository in VS Code or Jupyter.
2. Start a Python environment that has the dependencies installed.
3. Open `SunspotTracker.ipynb`.
4. Update the `path` variable in the notebook so it points to your local `Data` folder.
5. Run the cells in order.
6. Review the plotted centroid locations and the printed heliographic longitude and latitude values.

## Typical workflow

1. Select a FITS file from the data folder.
2. Display the map using `sunpy.map.Map`.
3. Crop the region around the sunspot.
4. Threshold the image to isolate the sunspot.
5. Compute the centroid of the masked region.
6. Transform the centroid to heliographic coordinates.
7. Repeat for multiple images.
8. Fit longitude versus day to estimate the rotation trend.

## Notes on the data path

The notebook currently uses absolute Windows paths in a few places. Before running it on another machine, replace those paths with a local path on your system. A relative path setup is recommended if you want the notebook to be easier to share.

## Output

The notebooks generate:

- centroid plots over the cropped sunspot region,
- heliographic longitude and latitude values,
- a linear fit showing longitude change over time.

## Limitations

- The centroid method depends on a manually chosen crop window and threshold.
- Results may vary if the image contrast changes or if the spot shape is complex.
- Some notebook cells use hard-coded file indexes, so the input order matters.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgment

This work uses the SunPy ecosystem for solar image analysis and coordinate conversion.

## Contributors

Ritu Raj\
Vinita Tiwari - tvinita309@gmail.com

# Carried out as a part of the ATSOAA Project in ARIES, Nanital.
