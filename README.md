# cloud-uploader
Command-Line (Bash) Sync Tool To Sync Files To Google Drive, Evernote &amp; My NAS 
Basic Prereqs are these:

sudo yum install -y incron
systemctl enable incrond
systemctl start incrond
incrontab -e
/data/scans IN_CREATE /usr/local/bin/cloud-uploader $@/$#
yum install grive2 -y
# Install geeknote: https://github.com/jeffkowalski/geeknote
sudo yum -y install git
git clone git://github.com/jeffkowalski/geeknote.git
sudo yum -y install python-pip
# - if you have only a python2 environment,
python setup.py build
sudo pip install --upgrade .
#add gdrive:  https://github.com/prasmussen/gdrive
wget -O gdrive https://docs.google.com/uc?id=0B3X9GlR6EmbnQ0FtZmJJUXEyRTA&export=download -o gdrive
sudo mv gdrive /usr/local/bin
sudo chmod ugo+x /usr/local/bin/gdrive
# Find Folder
# see: https://developers.google.com/drive/v3/web/search-parameters
gdrive list --name-width 0 --absolute --max 10 --query "name = 'scans'"
