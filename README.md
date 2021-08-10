# srb2dl

This script extracts links and information from mb.srb2.org, GitHub and GitLab and lists them in a simple format including title, author, upload/update date and category. This allows more straightforward and centralized approach to downloading everything related to SRB2 and SRB2Kart.

![srb2dl](https://user-images.githubusercontent.com/16626326/114288816-a7607d80-9a72-11eb-8509-a62fa1829405.gif)

**Features:**
- Browsing SRB2/SRB2Kart content by categories,
- Downloading multiple resources at the same time,
- Searching content by keyword or user,
- Filtering content by reusable,
- Added vanilla SRB2/SRB2Kart builds and custom builds (source code included),
- Runs on Linux and Windows (Cygwin, Git Bash).


**Dependencies:**
- GNU Coreutils,
- Bash or any POSIX compliant shell,
- Curl,
- Gawk,
- Optionally: w3m or any web browser for previewing resources in mb.srb2.org.

Additionally, Windows users need to have installed Cygwin or Git Bash to run this script.


**Dependencies Installation:**
- **Linux:**
In terminal enter this following commands:
1. Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install coreutils bash curl gawk`.
2. Arch/Arch based: `sudo pacman -S coreutils bash curl gawk`.
3. Gentoo: `sudo emerge coreutils bash curl gawk`.

- **Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 : ![video](https://youtu.be/SWYqp7iY_Tc?t=439)
2. Git Bash can be found on start menu.
3. The rest of dependencies are installed, if you followed video.

- **MacOS**:
In terminal enter this following command:
1. `brew install gawk curl` .

**Script Installation:**
- **Linux:**
1. Enter `git clone https://github.com/Bijman/srb2dl`,
2. Enter `sudo make install`, which will install to "/usr/bin" or "/usr/local/bin", if path exists, or just place script in your directory and change script's permissions to be executable: chmod 755 srb2dl.

- **Windows:**
1. Open Git Bash,
2. Go to your user directory (usuallly "C:/Users/[Your username]"): cd ~,
3. Enter `git clone https://github.com/Bijman/srb2dl`,
4. Create directory "bin" with command: `mkdir ~/bin`,
5. Copy script to "~/bin": `cp /path/to/srb2dl ~/bin`,
6. Change script's permissions to be executable: `chmod 755 ~/bin/srb2dl`,
7. Open text editor for "~/.bash_profile": `nano ~/.bash_profile`,
8. Write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in ~/.bash_profile,
9. Check if you set properly other environment variables from "Configuration" section,
10. Enter `source ~/.bash_profile` or restart Git Bash.

- **MacOS:**
1. Enter `git clone https://github.com/Bijman/srb2dl`,
2. Enter `sudo make install`, which will install to "/usr/local/bin", or just place script in your directory and change script's permissions to be executable: chmod 755 srb2dl.


**Usage (from help text):**
```
Download SRB2/SRB2Kart addons, software and builds.

Usage: srb2dl [OPTIONS...] <search-query> <directory-path>

  OPTIONS:

     -h, --help                             Show this help text

     -k, --kart                             Go to SRB2Kart resources

     -o, --old                              Go to archived resources for previous SRB2/SRB2Kart versions

     -r, --reusable                         Filter resources by reusable

     -s, --search         <search-query>    Search resources by keyword

     -u, --search-user    <search-query>    Search resources by user


  EXAMPLES:

     1. Show SRB2 resources and download them to chosen path:

            srb2dl "$HOME/Downloads"


     2. Go to SRB2Kart resources and download them to current directory:

            srb2dl --kart


     3. Search for Sonic related content:

            srb2dl --search "sonic"


     4. Search for user's reusable content:

            srb2dl --search-user "user123" --reusable


     5. Go to archived resources for previous SRB2/SRB2Kart versions and download them to "$HOME/Downloads" path (-r/--reusable option is not supported for -o/--old):

            srb2dl --old "$HOME/Downloads"

   Previewing resources is available by setting "export SRB2DLPREVIEW=1" and optionally variable BROWSER (for example "export BROWSER=firefox") in shell configuration file. Default previewer is w3m, if installed.
```
