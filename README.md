# STRETCH
STRETCH: A universal and modular conformation switching sensor harnessing mechanical force

This page contains the neccessary instructions for dowloading and running the provided code.
For the intial images captures, they are analyzed via ThunderStorm and Piccasso. A set of TEST/MOCK fiduciary markers are povided named as "COMDINED_TIFF.tif"

Instructions for Calculating Image registration Matrix:
01) Dowload said Combined_TIFF file.
02)Open the file on ImageJ/Fiji and split the two seperate channles via IMAGE-> Color-> Split channel

RUNNING THUNDERSTORM: PUNCTA LOCALIZATION
03)In order to run ThunderStorm for each seperate image, Plugin -> ThunderStorm ->Run Analysis
Please we aware: ThunderStorm has a pre-set camera setting. This can be changed by Plugi  -> ThunderStorm -> Camera Settings -> Enter the camera settings for the image analysis -> OK
Once the camera settings have been adjusted, perform the analysis by clicking "run analysis"

04)This will generate a .csv file with the x(nm)/y(nm) coordinates for the raw images
05) Once the information for the raw files have been saved.

RUNNING PICCASSO: PUNCTA LOCALIZATION: Please refer to the URL below for further instructions
https://picassosr.readthedocs.io/en/latest/localize.html


PERFORMING IMAGE REGISTRATION: TurboREG : plugins/TurboReg_.jar

https://bigwww.epfl.ch/thevenaz/turboreg/

01) Once two seperate files are opened image registration can be perfomed
02)One should be named the Source and the other the Target file. Here the Affine registration is performed.
03)Image registration can be performed with the Quality being "accurate" and the batch "Automatic" 
04) An output file will be generated. This will contain two stacks. The second stack should be deleted using Image -> Slice -> Delete Slice
05) The remaining image should be convereted into the same bit depth as the raw .TIFF files ( 16-bit image depth in this scenario)
06)The registered image can be saved and the puncta localized via ThuderStorm/Piccasso

PERFORMING DRIFT CORRECTION:STACKREG ImageJ Plugin : 

plugins/StackReg_.jar
https://bigwww.epfl.ch/thevenaz/stackreg/

01)For stackreg, the Affine drift correction is performed

Fiducial markers are localized using both software. Once localized, .csv file with said localizations are extracted. This .csv file is used for "IMAGE REG.py" The data is loaded to calculate the image registration matrix. 
Once a transformation matrix is calculated the information will be saved as a .txt file. This information will be used for the "DISTANCE CALC" code, where the calculated transformation matrix should be loaded into the designated location. A "MOCK" matrix has been loaded as a placeholder. 







