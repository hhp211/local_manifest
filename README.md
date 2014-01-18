Local_manifest.xml addon for building 

These files are to be placed in (Rom directory)/.repo/local_manifests,

after you initialize the repo but before you sync.


Getting Started
---------------

Make a build directory:

	mkdir Andoid (or whatever name you choose)
	cd Android (or the name  you chose)
	

To initialize your local repository using the AOSP manifest, use commands like these:

    repo init -u https://github.com/hhp211/local_manifest.git -b master
    
    curl -L -o .repo/local_manifest.xml -O -L https://github.com/hhp211/local_manifest.git

    	( or Download: https://github.com/hhp211/local_manifest.git
		and place it in ~/Android/.repo/local_manifest.xml (or ~/'name you chose'/.repo)

Then to sync up:

    repo sync --current-branch

And finally to build the AOSP ROM:

    . build/envsetup.sh
    lunch 
    (pick number of device)
    make -j4 or mka -j4
    
    You can also build a flashable zip with

mka otapackage


Look for out/target/product/device/ for the zip
