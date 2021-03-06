# TouchDesigner099-Slideshow

###### Tested and Developped on Windows 10 64-Bit Build 2017-14620

This is a slideshow I've created to accommodates my needs in my various TouchDesigner projects.

## Features
- Works with videos and images
- Preloads images to minimize impact on the application
- Choice of 5 types of transition
- Automatically adds new content added to your slideshow folder
- Slave mode that enables you to link multiple slideshow together 
- Bar in the UI shows the progression of the loading process

## Before using
- Make sure there's no special character in the path or file name. If so, you'll get an error and the loading will get stuck in the UI.
  - To fix this, rename or remove the badly named files and click on the *Reset* parameter

## How to use
1. Import the .tox
2. Connect a `TOP` to the `InputTOP` to set the resolution
3. Add a folder containing photos and/or videos in the *Images/Videos Folder* parameter.
   - If the folder exists and there's videos or images in it, the other parameters will be enabled
   

## Parameters
| Parameter                     | Description |
| ---------                     | -------------------------------------------- |
| Active                        | Start the slideshow's timer  |
| Reset                         | Reload all the content   |
|||
|||
| **Important!**|**Changes will take effect when you Reset the slideshow**|
| Randomize Order               | Randomize the order of folder's content.|
| Seed                          | Seed of the random  |  
| Multiply RGB by Alpha         | Activate the Multiply RGB by Alpha parameter from the *MovieFileInTOP* that loads the content | 
| Image Fit                   | Control how the content fits the input TOP  | 
| **__________**|**_____________________________________________________**|
|||
|||
| Images/Videos Folder          | Path of the folder containing photos and/or videos | 
|||
|||
| Display Length                | How long the content is displayed (sec)  | 
| Transition Speed              | How long for the transition to complete (sec)  | 
| Transition Style              | What kind of transition (None, L to R, R to L, T to B, B to T)  | 
| Next                          | Go to next content, This will automatically disable the *Active* parameter, the speed of the retrigger is based on the speed of the transition  | 
| Prev                          | Go to previous content, This will automatically disable the *Active* parameter, the speed of the retrigger is based on the speed of the transition  | 
|||
|||
| Over TOP                      | Path of a TOP you want to place on top of the slideshow  | 
| Fit                           | Controls how this TOP fits in the resolution of the slideshow (controlled by the input TOP)  | 
| Translate                     | Position of the Over TOP  | 
| Scale                         | Scale of the Over TOP  | 
|||
|||
| Use Video Duration            | If the current content is a video. Bypass the *Display Length* and uses the length of the video instead  | 
| When Video's Done             | Choose what happen when the video is done playing.<br />Start timer : Start the slideshow timer for the duration of the *Display Length* Parameter.<br />Trigger Next : Automatically trigger the animation and go to the next content  | 
|||
|||
| Slave Mode                    | Use this slideshow as a Slave. If so, everything except the *Transition Style*, *Over TOP*, will be controlled by the specified Master.  |
| Master Slideshow              | Path of the slideshow you want to use as Master. A message will appear if the path is valid.  |

## To do
- Remove media from the slideshow if he is removed from the slideshow folder
- Add a preview module that gives you the possibility to see what's coming next and go to that content.
- Change the communcation method between the UI and the Custom Parameters
- Fix a small black flash when the animation mode is set to None and we transition from a video to another video
- Stop TOP cooking when animation mode is set to None
