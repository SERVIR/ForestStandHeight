# Workshop Materials & Status
This includes the exercises for the workshop at SERVIR-Mekong: 
1. use FSH on data preprocessed in ISCE (study area: central Maine, US) --minor edits needed (some images may not be showing up correctly, need to include more detail on how to find the outputs or link to the slide deck that has this information)

2. ISCE installation --have been running on locally, so need to double check that everything works correctly on the Colab - specifically checking out the appropriate branch that is the stable version (v2.3.2)

3. preprocessing in ISCE --works, some images may not be appearing, need more info on how to find needed outputs or link to the slides with this information
In addition: I’m updating the FSH scripts for use with the ISCE-v2.3.2 output (the example data on GitHub used ISCE-v2.0.0). In auto_tree_height_single_ISCE.py I updated the capitalization on a couple lines so that the information could be located in the new isce.log format. However, there is one variable that doesn’t exist in the new outputs, baseline.perp_baseline , which I believe is the cause of the Index Error (the baseline.perp_baseline text can’t be found in the isce.log file, the strg list is empty, the [-1] element can’t be grabbed from the strg list). Lei Yang is looking into this, and Piyush Agram recommended that I look at 
https://github.com/isce-framework/isce2/blob/master/contrib/stack/stripmapStack/baseline.py for simple middle of scene estimate or
https://github.com/isce-framework/isce2/blob/master/contrib/stack/stripmapStack/baselineGrid.py to create a low res image of the baseline that captures the variation over the scene and take parts of the code and inject into runPreprocess step and have it report there. The simple middle of scene estimate should be fine. I'm trying to get this to work now.
Link to OVA & README for VM with ISCE installed and preprocessing troubleshooting in progress: https://drive.google.com/open?id=1FZel0LB4xdbigZTcRhP9pfXslBgrAafm
4. use FSH algorithm on study area Laos --more images on how to locate/format inputs, need isce.log to include baseline variables in order to calculate kz
