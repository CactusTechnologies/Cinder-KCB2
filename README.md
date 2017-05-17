Cinder-KCB2
===========

Cinder wrapper for Kinect 2 Common Bridge

===========

To enable face tracking on a TinderBox-generated project, add
this line to "Post-Build Events"

xcopy /e /i /y "$(KINECTSDK20_DIR)Redist\Face\$(PlatformTarget)\NuiDatabase" "$(OutDir)NuiDatabase"

## Updates

Use the v120 toolchain for projects.

Add #define NOMINMAX to the top of the project to prevent syntax errors arrising from std::min and std::max getting confused with macros ( throws the error  <i>error C2589: '(' : illegal token on right side of '::'</i> without it )

Need to change the <i>cinder-$(PlatformToolset).lib</i> to <i>cinder.lib</i> to Additional Dependencies under Linker > input 

Need to add <i>..\..\..\..\..\lib\msw\$(PlatformTarget)\Debug\v120</i> to Additional Library Directories under Linker > General.
