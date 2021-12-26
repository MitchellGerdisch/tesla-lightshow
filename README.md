# Introduction

Customized car model and lightshows for Model Y.

## Caveats and Disclaimers

- **USE AT YOUR OWN RISK**
  - Be sure to run outside of a garage or other obstructions.
- I make no attempt to be model agnostic. These are done for a Model Y.
  - That said, there is not reason they shouldn't work for any model.

# References

Tesla Getting Started: https://github.com/teslamotors/light-show

# Key Ideas/Points

- Create a main folder that has the following subfolders:

  - tesla_xlights_show_folder_modified
    - This folder should be left basically untouched other than MODEL edits (e.g. adding a submodel) made through the xlights tooling.
    - The tesla_xlights_show_modified folder contains submodels to isolate sets of lights on top of the show folder that is available from the tesla repo referenced above.
  - lightshow folders
    - These only contain the .wav, .fseq, .xsq folders generated by xlights

# Workflow

- Open xlights
  - File (xLights on Mac) > Preferences > Sequences > FSEQ Version, select "V2 Uncompressed"
- Open a new SHOW FOLDER - select the "tesla_xlights_show_modified" folder.
  - This version of the "Model S" model includes submodels for things like "lights only" or "front lights only" so that you can easily apply effects to subsets of nodes (i.e.lights, doors, windows).
  - Make sure the "3D" box is checked in the "Layouts" view.
- Create a new sequence or copy and modify an existing sequence.
  - New Sequence - Musical Sequence
    - Select .wav or .mp3 file
    - Choose Custom and set to 20ms frame interval
    - Select Quick Start
  - The panes may be sitting on top of each other and obscuring each other
    - Pull out the house preview to see the music timeline
    - Hit the Zoom buttons at the top right area to get better resolution of the music timeline.
  - Recommended panes (Note you can detach panes and float them as individual windows if you want by grabbing and moving):
    - Timeline,
    - House Preview,
    - Color windows,
    - Effect Settings

# Creating a Sequence - Tips and Tricks

- See https://github.com/teslamotors/light-show#boolean-light-channels for turning on and off lights and opening windows, etc.

- Adding timing tracks is critical to creating sections of the music in which you can drop effects.

  - Manually: click on the waveform where you want to put timing marks and press "t" to add a mark.
  - You can add automatic timing tracks by:
    - Right click on timing track
    - Select add timing track
    - Selet the drop down - if first time, select add Vamp plugin and do that, then restart xlights and add timing track.
    - BEST automatic timings:
      - Bars and Beats: Beats
      - Bars and Beats: Bars

- The "Single Strand" effect is a friend here. It provides easy ways to create cascades and flows along the lights.
- View -> Windows -> Effect Settings is your friend here since it allows you to change the settings for an effect.

# Creating Submodels

- Go to Layouts window
- Select "Tesla Model S"
- Double click the "Submodels" "..." in the model panel.
- Add a submodel
- Enter the node range(s) for the given submodel.
  - See the "tesla_node2light_mapping.csv" for the mapping of node numbers to names.
    - node numbering starts at 1 and goes to 46

# Prep for use in the car

- Run `python3 validator PATH_TO_FSEQ_FILE`

  - Confirm it passes validation.

- On a basically blank USB,

  - Create LightShow folder
  - In that folder put the .fseq and .wav (or .mp3) folders from the show you created.
  - Change their names to be "lightshow.fseq" and "lightshow.wav" on the stick.
