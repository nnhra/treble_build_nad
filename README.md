# NusantaraProject LTS 1.1 Android 10 GSI

## Variant
Examples
> NusantaraProject-LTS-1.1-a64-ab-vndklite-gapps-secure-20220511-UNOFFICIAL.img.xz

They are
```
ProjectName-{SNOW | SNOWLAND}-Miku-UI-version-a64-ab-vndklite-gapps-secure-BuildDate-Buildtype
 |                |                            |    |     |      |      |
 |                |                            |    |     |      |     Superuser removed and system props  
 |                |                            |    |     |     GMS    spoofed,for better chances of  
 |                |                            |    |     |            passing SafetyNet.
 |                |                            |    |     |
 |                |                            |    |    It is used for vndklite devices and 
 |                |                            |    |    supports system reading and writing.
 |                |                            |    |
 |                |                            |  Partition type, only AB variants are provided.(1)
 |                |                            |
 |                |                            |
 |                |                       CPU bits.
 |                |
 |     Android 12 | Android 12.1
 |
Miku UI
```

(1) Vendors of Android 9 and above support SAR(system-as-root), so GSI of AB partition type can be used.

## Build
To get started with building NusantaraProject GSI, you'll need to get familiar with [Git and Repo](https://source.android.com/source/using-repo.html) as well as [How to build a GSI](https://github.com/phhusson/treble_experimentations/wiki/How-to-build-a-GSI%3F).

- Install the repo command

Enter the following to download the repo binary and make it executable (runnable):

```
mkdir -p ~/bin
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
```

Put the ~/bin directory in your path of execution

In recent versions of Ubuntu, ~/bin should already be in your PATH. You can check this by opening ~/.profile with a text editor and verifying the following code exists (add it if it is missing):

```
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

Then, use this to update your environment.

```source ~/.profile```

- Install dependencies
    ```
    sudo apt-get install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5 libncurses5-dev libsdl1.2-dev libssl-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev xattr openjdk-11-jdk jq android-sdk-libsparse-utils -y
    ```
- Create a new working directory for your NusantaraProject build and navigate to it:
    ```
    mkdir nad-treble && cd nad-treble
    ```
- Clone this repo:
    ```
    git clone https://github.com/MizuNotCool/treble_build_nad -b lts
    ```
- Finally, start the build script:
    ```
    bash treble_build_nad/build.sh
    ```
