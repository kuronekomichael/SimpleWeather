# iOS8 Best Practices; A Weather App Case Stud

http://www.raywenderlich.com/55384/ios-7-best-practices-part-1

## XCode6でEmptyプロジェクトを作成する方法

http://stackoverflow.com/questions/25783282/how-to-create-an-empty-application-in-xcode-6-without-storyboard

1. Xcodeで新しいプロジェクトを作成し、`Single View Application`を選択する
2. Remove Main.storyboard and LaunchScreen.xib (select them, right-click, and choose to either remove them from the project, or delete them completely).

```
$ rm SimpleWeather/Base.lproj/Main.storyboard
$ rm SimpleWeather/Base.lproj/LaunchScreen.xib
```

3. `Info.plist`から、"Main storyboard file base name"と"Launch screen interface file base name"のエントリを削除する
4. `AppDelegate.m`を開いて、`applicationDidFinishLaunchingWithOptions`メソッドを下記のように修正する:

```
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
    // Override point for customization after application launch.
    self.window.backgroundColor = [UIColor whiteColor];
    [self.window makeKeyAndVisible];
    return YES;
}
```

$ cd SimpleWeather
$ pod init
$ echo "pod 'Mantle'" >> Podfile
$ echo "pod 'LBBlurredImage'" >> Podfile
$ echo "pod 'TSMessages'" >> Podfile
$ echo "pod 'ReactiveCocoa'" >> Podfile
$ pod install
$ open SimpleWeather.xcworkspace
