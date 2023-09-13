# slspec

### Summary

The [slspec file](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy/UsersGuide#A--slspec:~:text=%2D%2D-,slspec,-Specifies%20a%20text) describes how the slices/MB-groups of MRI were acquired. It is needed to correct for body motion in the volume using [FSL's eddy --mporder option](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddy/UsersGuide#A--slspec:~:text=the%20next%20release.-,%2D%2Dmporder,-If%20one%20wants). Please see the FSL website for detail.
This jupyter-notebook automatically creates the slspec text file using the json file made when the dicom image is converted using dcm2niix.

It supports multiband 1 (no multiband) to multiband 8. It was tested for GE and Siemens, multiband 1, 2, 4, 8. Please inform me if it doesn't work well.

### Required library

pandas

### Instructions

1. Replace the json file name 'DWI.json' in the first cell with the json file name of the image for which you want to create a slspec file.
2. Put it in the same folder, or specify the path.
3. Now run all the cells and the slspec file will be created in the folder where the notebook is located.

Note that the json file must contain 'SliceTiming'.
