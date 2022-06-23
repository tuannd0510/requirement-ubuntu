https://tesseract-ocr.github.io/tessdoc/Compiling-%E2%80%93-GitInstallation.html#post-install-instructions

'''
sudo apt-get install automake ca-certificates g++ git libtool libleptonica-dev make pkg-config
cd tesseract
./autogen.sh
./configure
make
sudo make install
sudo ldconfig
'''
