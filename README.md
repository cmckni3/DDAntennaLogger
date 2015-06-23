# DDAntennaLogger

**CocoaLumberjack Custom Logger for Remote Logging with Antenna**

The easiest way to leverage on logging power of [CocoaLumberjack](https://github.com/CocoaLumberjack/CocoaLumberjack) and logging remotely with the simplicity of [Antenna](https://github.com/mattt/Antenna).

### Install

```
pod 'DDAntennaLogger', '1.0.0'
```

### Usage

Somewhere, for example in your `AppDelegate`:

```objc
NSString *yourServerURLString = @"...";
NSString *yourServerLogMethod = @"..."; // Could be POST or LOG, or any other supported by your server
[[Antenna sharedLogger] addChannelWithURL:[NSURL URLWithString:yourServerURLString] method:yourServerLogMethod];
[[Antenna sharedLogger] startLoggingApplicationLifecycleNotifications];

DDAntennaLogger *logger = [[DDAntennaLogger alloc] initWithAntenna:[Antenna sharedLogger]];
[DDLog addLogger:logger];

DDLogInfo(@"DDAntennaLogger is cool!");
// => You'll see "DDAntennaLogger is cool!" on your server :)
```

It's **that** easy 👍

You may also want to checkout [this post](http://marius.me.uk/blog/2015/04/remote-logging-using-cocoalumberjack-antenna-ddantennalogger/) to read about a real world used of DDAntennaLogger.

### Contact

[Giovanni Lodi](http://giovannilodi.com) [@mokagio](https://twitter.com/mokagio)

### Special Thanks

This project was after a quick conversation between [@sandfoxuk](http://twitter.com/sandfoxuk) and me, to solve the need of [BIZZBY](https://github.com/Bizzby) to get deep insight on the code execution while trying to solve a nasty bug.

### License

MIT

