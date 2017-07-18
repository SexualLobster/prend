prender.c:	The portal rendering example program that I created in this video. This is C source code, so you need to compile it before you can run it. You will need libSDL as well.
map-clear.txt:	The map file that you need to run prender.c. It is a simplified version of the actual map.txt file used by the fully-featured program.
portrend.c:	The fully featured portal rendering program. Please edit the section containing various #defines before compiling. Explanation of the various features:
	#define DepthShading
		If defined, depth shading is enabled. Otherwise single-color walls are rendered. Has no effect if TextureMapping is enabled.
	#define VisibilityTracking
		If defined, the program will keep track of which floors and ceilings are currently visible in the player's view. When you hold the TAB key to see the map, these visible areas will be colored in a particular manner.
	#define TextureMapping
		When enabled, walls, floors and ceilings will be texture-mapped instead of single color. You must download textures.7z and extract it for that to work. Enabling this #define will also override DepthShading.
	#define LightMapping
		When enabled, texture mapped walls are rendered with light-maps. You must run the program with the --rebuild parameter at least once for the lightmaps to work. Rebuilding the lightmaps involves ray tracing and will take hours of time, but only has to be done once. Note that this will produce a 4'798'283'776 byte file on your disk. Note also that the LightMapping code can only be compiled on 64-bit POSIX systems (Linux et al), because it uses the mmap system call, and the file to be mapped is over 4 gigabytes in size. It also requires OpenMP support (-fopenmp compiler option in Clang and GCC). Has no effect unless TextureMapping is also enabled.
textures.7z:	This ZIP 7Z file contains the textures and normalmaps. These textures and normalmaps are PPM files with 1024x1024 size, and they are downloaded from http://opengameart.org/content/50-free-textures-4-normalmaps under the CC0 license (public domain).
actions-log.zip:A file called "actions.log". What might it be for?
map.txt:	The actual map file. map-clear.txt was the same map for a less feature-rich program that could not read this file.