# Building with Xcode: Trouble Shooting
This file describes some troubles I met when build with Xcode from official master brench and how I solved them. Note that the solutions may not be the good ones or even the right ones, it just works on my computer, that is it.

### Tested System
 * Xcode 12.4 or higher
 * Mac OS X 11.2.2 or higher
 

## Library
* Add **lib** and **Headers** yourself:  
Add these folders in the project folder (where the project file exists) and then copy the necessary library and header files yourself into these folders.  
(These folders will be ignored by git.)

* header not found:
Install the proper library via homebrew and copy the include folder (from the library) into the **Headers** folder.

* Library not found:
Install the proper library via homebrew and copy the necessary lib files into the **lib** folder.

* readline8.0 library not found:
The version that can be downloaded from homebrew is higher than 8.0 but the 8.0 library is needed.  
Go the the settings of TARGETS "The Battle for Wesnoth", the **General** bar, and found the **readline8.0** in **Frameworks, Libraries and Embedded Content** and delete it. Then Add the readline8.1.dylib.

* "Use of undeclared identifier 'history_list'" or "Use of undeclared identifier 'append_history'":  
These functions are from **readline** library. But when I tried to install it via homebrew, I was told that the lastest version is already installed.  
To fix it, use "brew reinstall readline" and copy it to the lib folder manually.  
About the reason:  
https://github.com/YosysHQ/yosys/issues/301#issuecomment-275909611s

* xxx library validation fails because of different Team IDs  
After installing all those libraries, I finally got the project built successfully. However, the game crashed just after launching with error messages above.  
The solution:  
https://developer.apple.com/forums/thread/126895  
Although the solution B is perferred in the link above, if you just want to practice coding locally, the solution A is much faster.

## Necessary Headers
* boost  
* cairo  
* glib-2.0  
* harfbuzz  
* SDL2  
* pango  
* vorbis  
* ogg  
* readline  
* fontconfig  

(Maybe some other sdl2_xx headers are also needed)  

## Necessary Lib
* libSDL2-2.0.0.dylib  
* libfribidi.0.dylib  
* libSDL2_image-2.0.0.dylib  
* libgio-2.0.0.dylib  
* libSDL2_mixer-2.0.0.dylib  
* libglib-2.0.0.dylib  
* libSDL2_net-2.0.0.dylib  
* libgmodule-2.0.0.dylib  
* libSDL2_ttf-2.0.0.dylib  
* libgobject-2.0.0.dylib  
* libboost_chrono-mt.dylib  
* libgraphite2.3.dylib
* libboost_context-mt.dylib 
* libgthread-2.0.0.dylib
* libboost_coroutine-mt.dylib  
* libharfbuzz.0.dylib
* libboost_filesystem-mt.dylib  
* libintl.8.dylib
* libboost_iostreams-mt.dylib  
* libogg.0.dylib
* libboost_locale-mt.dylib 
* libpango-1.0.0.dylib
* libboost_program_options-mt.dylib  
* libpangocairo-1.0.0.dylib  
* libboost_random-mt.dylib  
* libpangoft2-1.0.0.dylib  
* libboost_regex-mt.dylib  
* libpcre.1.dylib  
* libboost_system-mt.dylib  
* libpixman-1.0.dylib  
* libboost_thread-mt.dylib  
* libpng16.16.dylib
* libcairo.2.dylib  
* libreadline.8.1.dylib  
* libcrypto.1.1.dylib  
* libssl.1.1.dylib
* libffi.7.dylib
* libvorbis.0.dylib
* libfontconfig.1.dylib  
* libvorbisfile.dylib
* libfreetype.6.dylib
* libz.1.dylib