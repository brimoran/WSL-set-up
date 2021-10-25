# WSL-set-up

#Check what we have
cat /etc/debian_version
echo $0
apt list --installed

# Get VIM
sudo apt-get update
sudo apt-get upgrade --fix-missing
sudo apt install vim

# Upgrade to Debian 10 Buster
sudo vim  /etc/apt/sources.list # change all references to stretch to buster
sudo apt-get update && sudo apt-get upgrade --fix-missing
sudo apt full-upgrade
exit
cat /etc/debian_version

# Python 3
sudo apt install python3
sudo apt install python3-pip
sudo apt-get install python3-pandas
pip3 install boto3
pip3 install msoffcrypto-tool

# Various tools
wget "https://github.com/jgm/pandoc/releases/download/2.15/pandoc-2.15-1-amd64.deb"
sudo dpkg -i /home/brian/pandoc-2.15-1-amd64.deb 
sudo apt-get install poppler-utils
sudo apt-get install ghostscript --fix-missing
sudo apt-get install p7zip-full
sudo apt-get install filezilla
sudo apt-get install xlsx2csv
sudo apt install mosh
sudo apt install htop
htop # check on number of cores for R install
sudo apt install curl

# Git
git config --global user.name "Your Name"
sudo apt-get install git
git config --global user.name "Your Name"
git config --global user.email youremail@provider.com
git config --list

# Create a SSH key
ssh-keygen -t rsa -b 4096 -C "brimoran@hotmail.com"
cat ~/.ssh/id_rsa.pub
ls

# Tidy
rm pandoc-2.15-1-amd64.deb 

# Clone repos
mkdir version-controlled
cd version-controlled/
git clone git@YOURREPO

# Install VIM plugins
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

# Copy vimrc from repo
cd TO CORRECT FOLDER
cp .vimrc ~/

# Add R version 4 to sources list
sudo vim /etc/apt/sources.list

```
deb [trusted=yes allow-insecure=yes allow-downgrade-to-insecure=yes] http://cloud.r-project.org/bin/linux/debian buster-cran40/
```

sudo apt update
sudo apt install -t buster-cran40 r-base --fix-missing

# Install packages that my R set up needs
sudo apt install libssl-dev
sudo apt install openssh
sudo apt install openssl
sudo apt install libxml2-dev
sudo apt install libcurl4-openssl-dev
sudo apt install libudunits2-dev
sudo apt install libv8-dev
sudo apt install libfontconfig1-dev
sudo apt-get install libgdal-dev libproj-dev

# Enter R and download R libraries
sudo R

```r
install.packages(c("ggplot2","tidyverse","knitr","ggthemes","scales","ggmap","mapproj","plotly","ggfortify","leaflet","leaflet.extras","rgdal","forecast","treemapify","dbscan","survival","googleVis","rmarkdown","flexdashboard","highcharter","devtools","maptools","mapview","treemap","networkD3","visNetwork","DiagrammeR","DT","ggcorrplot", "Hmisc", "anomalize", "fpp2", "h2o", "sweep", "timetk", "xgboost", "prophet","survminer","ggwordcloud","this.path", "ggsn") , repo = 'https://mac.R-project.org', ask = FALSE, checkBuilt = TRUE, Ncpus = 4)
```

# R studio
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/server/bionic/amd64/rstudio-server-2021.09.0-351-amd64.deb
sudo gdebi rstudio-server-2021.09.0-351-amd64.deb

# LaTeX
sudo apt install perl perl-doc
wget "http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz"
tar -xzf install-tl-unx.tar.gz
cd install-tl-20211025/
sudo ./install-tl

# Add LaTeX and msoffcrypto-tool to PATH
cd
vim .bashrc 

```
PATH=/usr/local/texlive/2021/bin/x86_64-linux:$PATH

MANPATH=/usr/local/texlive/2021/texmf-dist/doc/man

INFOPATH=/usr/local/texlive/2021/texmf-dist/doc/info

PATH=$HOME/.local/bin:$PATH
```

# Tidy
rm -r install-tl-*
rm *.deb
vim .bashrc 

# Check
pdflatex --version

