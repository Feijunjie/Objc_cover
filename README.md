# Objc_cover
iOS中用于检测程序启动时候没有用到的代码

Say you have this Objective-C code:

    - (void)notUsed {
    	return;
    }
    
    - (void)actuallyUsed {
    	return;
    }
    
    // ...
    
    [self actuallyUsed];

Thanks to /usr/bin/otool, you can get clues about potentially unused methods, like this:

    $ python objc_cover.py /Users/nst/Desktop/iCalReport 
    # the following methods may be unreferenced
    -[MyClass notUsed]


