This script extracts links and information from mb.srb2.org, GitHub and GitLab and lists them in a simple format including title, author, upload/update date and category. This allows more straightforward and centralized approach to downloading everything related to SRB2, SRB2Kart and Ring Racers.

![srb2dl](https://github.com/Bijman/srb2dl/assets/16626326/4ba1ecbc-965c-4233-80ab-e7c92f66acaf)

# Features
- Browsing SRB2/SRB2Kart/Ring Racers content by categories,
- Downloading multiple resources at the same time,
- Downloading resource by addon ID,
- Searching content by keyword or user,
- Filtering content by reusable,
- Upgrade previously downloaded content,
- Added vanilla SRB2/SRB2Kart/Ring Racers builds and custom builds (source code included),
- Runs on Linux, Windows (Cygwin, Git Bash) and MacOS.

# Dependencies
- Basic system utilities like GNU Coreutils, BusyBox or macOS out-of-the-box system utilities,
- Bash or any POSIX compliant shell,
- Findutils,
- Curl,
- Gawk,
- Ncurses,
- Optionally: w3m or any web browser for previewing resources in mb.srb2.org.

Additionally, Windows users need to have installed Cygwin or Git Bash to run this script.

# Dependencies Installation
**Linux:**
1. In terminal enter this following command:
- Debian/Ubuntu/Debian based/Ubuntu based: `sudo apt install make git coreutils findutils ncurses-bin curl gawk`,

- Arch/Arch based: `sudo pacman -S --needed make git coreutils findutils ncurses curl gawk`,

- Gentoo/Gentoo based: `sudo emerge -av dev-vcs/git sys-apps/coreutils sys-apps/findutils sys-libs/ncurses net-misc/curl sys-apps/gawk`,

- Fedora/Fedora based: `sudo dnf install make git coreutils findutils ncurses curl gawk`,

- Fedora Silverblue/Fedora Kinoite/Universal Blue (Baazite, Aurora): `rpm-ostree install -A --allow-inactive make git coreutils findutils ncurses curl gawk`,

- RHEL/RHEL based: `sudo dnf install make git coreutils findutils ncurses curl gawk`,

- openSUSE Leap/openSUSE Tumbleweed/openSUSE Leap based/openSUSE Tumbleweed based: `sudo zypper in make git coreutils findutils ncurses curl gawk`,

- openSUSE MicroOS/openSUSE MicroOS based: `sudo transactional-update pkg in make git coreutils findutils ncurses curl gawk`,

- Void/Void based: `sudo xbps-install -S make git coreutils findutils ncurses curl gawk`,

- Alpine/Alpine based: `sudo apk add make git coreutils findutils ncurses curl gawk`,

- Solus/Solus based: `sudo eopkg it make git coreutils findutils ncurses curl gawk`,

- NixOS/NixOS based: `sudo nix profile install nixpkgs#gnumake nixpkgs#git nixpkgs#coreutils nixpkgs#findutils nixpkgs#ncurses nixpkgs#curl nixpkgs#gawk --extra-experimental-features 'nix-command flakes'` or set those packages in "environment.systemPackages = with pkgs;" in "/etc/nixos/configuration.nix", and then enter `sudo nixos-rebuild switch`.

- Immutable systems like Steam Deck's SteamOS need rootless method of getting dependencies to avoid issues with wiping out installed packages after system's update or not to be able to write to certain path, like "/usr/local":
	- [Homebrew](https://brew.sh/): `brew install make git coreutils findutils ncurses curl gawk`.

**Windows:**
1. Installing Git Bash:
- Watch this video from 7:19 to 9:33 in [HERE](https://youtu.be/SWYqp7iY_Tc?t=439),

2. Git Bash can be found on start menu,

3. The rest of dependencies are installed, if you followed video.

**MacOS:**
1. In terminal enter this following command:
- Homebrew: `brew install curl gawk`,
- MacPorts: `sudo port install curl gawk`.

# Installation
**Linux:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2dl`,

3. Enter `sudo make install`, which will install to "/usr/local/bin". You can specify your path with variable PREFIX, for example `make install PREFIX=$HOME/.local`, which will copy script to "$HOME/.local/bin". Alternatively manually place script to your path, which is readable by shell (PATH environment variable), and change script's permissions to be executable: `chmod 755 [path to srb2dl script]`,

4. Go to downloaded directory: `cd srb2dl`.

**Windows:**
1. Open Git Bash,

2. Go to your user directory (usuallly "C:/Users/[Your username]"): `cd ~`,

3. Enter `git clone https://github.com/Bijman/srb2dl`,

4. Create directory "bin" with command: `mkdir ~/bin`,

5. Copy script to "~/bin": `cp ~/srb2dl/srb2dl ~/bin`,

6. Change script's permissions to be executable: `chmod 755 ~/bin/srb2dl`,

7. Open text editor for "~/.bash_profile": `nano ~/.bash_profile`,

8. In the opened text editor from previous step write new path to executables with environment variable PATH like `export PATH="~/bin:$PATH"` in "~/.bash_profile",

9. Enter `source ~/.bash_profile` or restart Cygwin or Git Bash.

**MacOS:**
1. Open terminal,

2. Enter `git clone https://github.com/Bijman/srb2dl`,

3. Go to downloaded directory: `cd srb2dl`,

4. Enter `sudo make install`, which will install to "/usr/local/bin". You can specify your path with variable PREFIX, for example `make install PREFIX=$HOME/.local`, which will copy script to "$HOME/.local/bin". Alternatively manually place script to your path, which is readable by shell (PATH environment variable), and change script's permissions to be executable: `chmod 755 [path to srb2dl script]`.

# Usage (from help text)
```
Download SRB2/SRB2Kart/Ring Racers addons, software and builds.

Usage: srb2dl [OPTIONS...] <addon-id/search-query> <directory-path>

  OPTIONS:

     -h, --help                             Show this help text.

     -hst, --history      <addon-id>        Choose version of resource by mb.srb2.org addon ID and download it.

     -i, --id             <addon-id>        Download resource by mb.srb2.org addon ID.

     -k, --kart                             Go to SRB2Kart resources.

     -kr, --ringracers                      Go to Ring Racers resources.

     -lu, --listurl                         List URL from database of downloaded files.

     -o, --old                              Go to archived resources for previous SRB2/SRB2Kart/Ring Racers versions.

     -ru, --removeurl                       Remove URL from database of downloaded files (preventing of upgrading undesired resources).

     -r, --reusable                         Filter resources by reusable.

     -s, --search         <search-query>    Search resources by keyword.

     -u, --search-user    <search-query>    Search resources by user.

     -up, --upgrade                         Upgrade previously downloaded resources, according to database of URLs (only mb.srb2.org is supported).

  EXAMPLES:

     1. Show SRB2 resources and download them to chosen path:

            srb2dl "$HOME/Downloads"


     2. Go to Ring Racers resources and download them to current directory:

            srb2dl --ringracers


     3. Search for Sonic related content:

            srb2dl --search "sonic"


     4. Search for user's reusable content:

            srb2dl --search-user "user123" --reusable


     5. Go to archived resources for previous SRB2/SRB2Kart/Ring Racers versions and download them to "$HOME/Downloads" path (-r/--reusable option is not supported for -o/--old):

            srb2dl --old "$HOME/Downloads"


     6. Upgrade previously downloaded resources to "$HOME/Downloads" path, according to database of URLs (only mb.srb2.org is supported):

            srb2dl --upgrade "$HOME/Downloads"


     7. Remove URL from database of downloaded files (preventing of upgrading undesired resources):

            srb2dl --removeurl


     8. Download resource by addon ID and download it to "$HOME/Downloads" path:

            srb2dl --id 3457 "$HOME/Downloads"


     9. Choose version of resource by addon ID and download it to "$HOME/Downloads" path:

            srb2dl --history 3457 "$HOME/Downloads"

  NOTES:
     1. Previewing resources is available by setting "export SRB2DLPREVIEW=1" and optionally variable BROWSER (for example "export BROWSER=firefox") in shell configuration file. Default previewer is w3m, if installed.

     2. If you set "export SRB2DLAUTODIR=1" in shell configuration file, script will be able to detect path to SRB2 configuration folder and then let you choose subdirectory, where each addon will be downloaded. WARNING: parsing path to download resource as script's argument is disabled, when this variable is set.

     3. Other environment variables to use. To activate them with value "1", do for example "export SRB2DLDEBUG=1":

         - SRB2DLDEBUG - Getting verbose output from script. Useful for reporting issues in https://github.com/bijman/srb2dl/issues.
```

# Notes
1. Previewing resources is available by setting "export SRB2DLPREVIEW=1" and optionally variable BROWSER (for example "export BROWSER=firefox") in shell configuration file. Default previewer is w3m, if installed.

2. If you set "export SRB2DLAUTODIR=1" in shell configuration file, script will be able to detect path to SRB2 configuration folder and then let you choose subdirectory, where each addon will be downloaded. WARNING: parsing path to download resource as script's argument is disabled, when this variable is set.

3. Other environment variables to use. To activate them with value "1", do for example "export SRB2DLDEBUG=1":

	- SRB2DLDEBUG - Getting verbose output from script. Useful for reporting issues in https://github.com/bijman/srb2dl/issues.

