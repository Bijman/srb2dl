This script extracts links and information from mb.srb2.org, GitHub and GitLab and lists them in a simple format including title, author, upload/update date and category. This allows more straightforward and centralized approach to downloading everything related to SRB2 and SRB2Kart.

![srb2dl](https://user-images.githubusercontent.com/16626326/114288816-a7607d80-9a72-11eb-8509-a62fa1829405.gif)

# Features
- Browsing SRB2/SRB2Kart content by categories,
- Downloading multiple resources at the same time,
- Searching content by keyword or user,
- Filtering content by reusable,
- Added vanilla SRB2/SRB2Kart builds and custom builds (source code included),
- Runs on Linux, Windows (Cygwin, Git Bash) and MacOS.

# Dependencies
- GNU Coreutils,
- Bash or any POSIX compliant shell,
- Curl,
- Gawk,
- Ncurses,
- Optionally: w3m or any web browser for previewing resources in mb.srb2.org.

Additionally, Windows users need to have installed Cygwin or Git Bash to run this script.

# Dependencies Installation
**Linux:**
1. In terminal enter this following command:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install coreutils bash ncurses-bin curl gawk`,
- Arch/Arch based: `sudo pacman -S coreutils bash ncurses curl gawk`,
- Gentoo: `sudo emerge coreutils bash ncurses curl gawk`,
- Fedora/Fedora based: `sudo dnf install make git coreutils findutils bash ncurses curl gawk`,
- OpenSUSE/OpenSUSE based: `sudo zypper in make git coreutils findutils bash ncurses curl gawk`,
- Void/Void based: `sudo xbps-install -S make git coreutils findutils bash ncurses curl gawk`,
- Alpine/Alpine based: `sudo apk add make git coreutils findutils bash ncurses curl gawk`,
- Solus/Solus based: `sudo eopkg it make git coreutils findutils bash ncurses curl gawk`,
- NixOS/NixOS based: `sudo nix-env -i gnumake git coreutils findutils bash ncurses curl gawk` or set those packages in "environment.systemPackages = with pkgs;" in "/etc/nixos/configuration.nix", and then enter `sudo nixos-rebuild switch`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. The rest of dependencies are installed, if you followed video.

**MacOS:**
1. In terminal enter this following command:
- Homebrew: `brew install curl gawk`,
- MacPorts: `sudo port install curl gawk`.

# Script Installation
**Linux:**
1. Enter `git clone https://github.com/Bijman/srb2dl`,

2. Enter `sudo make install`, which will install to "/usr/bin" or "/usr/local/bin", if path exists, or just place script in your directory and change script's permissions to be executable: `chmod 755 srb2dl`.

3. Go to downloaded directory: `cd srb2bld`,

**Windows:**
1. Open Git Bash,

2. Go to your user directory (usuallly "C:/Users/[Your username]"): `cd ~`,

3. Enter `git clone https://github.com/Bijman/srb2dl`,

4. Create directory "bin" with command: `mkdir ~/bin`,

5. Copy script to "~/bin": `cp ~/srb2dl/srb2dl ~/bin`,

6. Change script's permissions to be executable: `chmod 755 ~/bin/srb2dl`,

7. In the opened text editor from previous step write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in "~/.bash_profile",

8. Write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in "~/.bash_profile",

9. Enter `source ~/.bash_profile` or restart Cygwin or Git Bash.

**MacOS:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2dl`,

3. Go to downloaded directory: `cd srb2dl`,

4. Enter `sudo make install`, which will install to "/usr/local/bin", if path exists. Alternatively manually place script to your path, which is readable by shell (PATH environment variable), and change script's permissions to be executable: `chmod 755 [path to srb2dl script]`.

# Usage (from help text)
```
Download SRB2/SRB2Kart addons, software and builds.

Usage: srb2dl [OPTIONS...] <search-query> <directory-path>

  OPTIONS:

     -h, --help                             Show this help text.

     -k, --kart                             Go to SRB2Kart resources.

     -o, --old                              Go to archived resources for previous SRB2/SRB2Kart versions.

     -r, --reusable                         Filter resources by reusable.

     -s, --search         <search-query>    Search resources by keyword.

     -u, --search-user    <search-query>    Search resources by user.


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

# Added features/content

**2021-08-11:**
1. Download archived content for previous versions of SRB2 and SRB2Kart.

![srb2dlold](https://user-images.githubusercontent.com/16626326/128992658-eab52b02-78dc-45e6-9715-5759904c7de1.gif)
