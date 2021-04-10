# srb2dl

This script extracts links and information from mb.srb2.org, GitHub and GitLab and lists them in a simple format including title, author, upload/update date and category. This allows more straightforward and centralized approach to downloading everything related to SRB2 and SRB2Kart.

Features:
    - Browsing SRB2/SRB2Kart content by categories,
    - Downloading multiple resources at the same time,
    - Searching content by keyword or user,
    - Filtering content by reusable,
    - Added vanilla SRB2/SRB2Kart builds and custom builds (source code included),
    - Runs on Linux and Windows (Cygwin, Git Bash),

Dependencies:
    - GNU Coreutils,
    - Bash or any POSIX compliant shell,
    - Curl,
    - Gawk,
    - Optionally: w3m or any web browser for previewing resources in mb.srb2.org.

Additionally, Windows users need to have installed Cygwin or Git Bash to run this script.


Usage (from help text):
Download SRB2/SRB2Kart addons, software and builds.

Usage: srb2dl [OPTIONS...] <search-query> <directory-path>

  OPTIONS:

     -h, --help                             Show this help text

     -k, --kart                             Go to SRB2Kart resources

     -r, --reusable                         Filter resources by reusable

     -s, --search         <search-query>    Search resources by keyword

     -a, --search-user    <search-query>    Search resources by user


  EXAMPLES:

     1. Show SRB2 resources and download them to chosen path:

            srb2dl ~/Downloads


     2. Go to SRB2Kart resources and download them to current directory:

            srb2dl --kart


     3. Search for Sonic related content:

            srb2dl --search "sonic"


     4. Search for user's reusable content:

            srb2dl --search-user "user123" --reusable


   Previewing resources is available by setting "export SRB2DLPREVIEW=1" and optionally variable BROWSER (for example "export BROWSER=firefox") in shell configuration file. Default previewer is w3m, if installed.
