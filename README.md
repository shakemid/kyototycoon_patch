Kyoto Tycoon Solaris event ports patch
=================

Patch for Kyoto Tycoon to be able to use Solaris event ports

# Install
Install process for Solaris 11 is following. It can be installed to Solaris 10 with gcc4.
- Install gcc4 and lua
```
pkg install gcc4
pkg install lua
```
- Install Kyoto Cabinet
```
tar zxvf kyotocabinet-1.2.76.tar.gz
cd kyotocabinet-1.2.76
./configure --prerix=/opt/kyotocabinet LDFLAGS='-L/opt/kyotocabinet/lib -R/opt/kyotocabinet/lib'
make
make install
```
- Patch to Kyoto Tycoon
```
tar zxvf kyototycoon-0.9.56.tar.gz
cd kyototycoon-0.9.56
patch -i kyototycoon-0.9.56-solaris-eventports-patch
```
- Install Kyoto Tycoon
```
./configure --prerix=/opt/kyototycoon --with-kc=/opt/kyotocabinet LDFLAGS='-L/opt/kyototycoon/lib -R/opt/kyototycoon/lib -L/opt/kyotocabinet/lib -R/opt/kyotocabinet/lib'
make
make install
```

# Changes
## 0.0.1 (2014-08-30)
- Initial commit

# Links
- Kyoto Cabinet: http://fallabs.com/kyotocabinet/
- Kyoto Tycoon: http://fallabs.com/kyototycoon/

# Author
K.Cima k-cima[at]kendama.asia

