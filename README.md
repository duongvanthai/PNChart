#PNChart

A simple and beautiful chart lib with **animation** used in [Piner](https://itunes.apple.com/us/app/piner/id637706410) and [CoinsMan](https://itunes.apple.com/us/app/coinsman/id772163893) for iOS

[![](https://dl.dropboxusercontent.com/u/1599662/pnchart.gif)](https://dl.dropboxusercontent.com/u/1599662/pnchart.gif)

## Requirements

PNChart works on iOS 6.0 and later version and is compatible with ARC projects. It depends on the following Apple frameworks, which should already be included with most Xcode templates:

* Foundation.framework
* UIKit.framework
* CoreGraphics.framework
* QuartzCore.framework

You will need LLVM 3.0 or later in order to build PNChart.




## Usage

### Cocoapods

[CocoaPods](http://cocoapods.org) is the recommended way to add PNChart to your project.

1. Add a pod entry for PNChart to your Podfile `pod 'PNChart', '~> 0.2.2'`
2. Install the pod(s) by running `pod install`.
3. Include PNChart wherever you need it with `#import "PNChart.h"`.


### Copy the PNChart folder to your project


[![](https://dl.dropboxusercontent.com/u/1599662/line.png)](https://dl.dropboxusercontent.com/u/1599662/line.png)

```objective-c
  #import "PNChart.h"

  //For LineChart
  PNLineChart * lineChart = [[PNLineChart alloc] initWithFrame:CGRectMake(0, 135.0, SCREEN_WIDTH, 200.0)];
  [lineChart setXLabels:@[@"SEP 1",@"SEP 2",@"SEP 3",@"SEP 4",@"SEP 5"]];
  [lineChart setYValues:@[@1, @10, @2, @6, @3]];
  [lineChart strokeChart];

```

[![](https://dl.dropboxusercontent.com/u/1599662/bar.png)](https://dl.dropboxusercontent.com/u/1599662/bar.png)

```objective-c
  #import "PNChart.h"

  //For BarChart
  PNBarChart * barChart = [[PNBarChart alloc] initWithFrame:CGRectMake(0, 135.0, SCREEN_WIDTH, 200.0)];
  [barChart setXLabels:@[@"SEP 1",@"SEP 2",@"SEP 3",@"SEP 4",@"SEP 5"]];
  [barChart setYValues:@[@1,  @10, @2, @6, @3]];
  [barChart strokeChart];

```

[![](https://dl.dropboxusercontent.com/u/1599662/circle.png)](https://dl.dropboxusercontent.com/u/1599662/circle.png)


```objective-c
#import "PNChart.h"

//For CircleChart

PNCircleChart * circleChart = [[PNCircleChart alloc] initWithFrame:CGRectMake(0, 80.0, SCREEN_WIDTH, 100.0) andTotal:[NSNumber numberWithInt:100] andCurrent:[NSNumber numberWithInt:60]];
circleChart.backgroundColor = [UIColor clearColor];
[circleChart setStrokeColor:PNGreen];
[circleChart strokeChart];

```

#### Callback

Currently callback only works on Linechart

```objective-c
  #import "PNChart.h"

//For LineChart

lineChart.delegate = self;


```

```objective-c

//For DelegateMethod


-(void)userClickedOnLineKeyPoint:(CGPoint)point andPointIndex:(NSInteger)index{
    NSLog(@"Click Key on line %f, %f and index is %d",point.x, point.y,index);
}

-(void)userClickedOnLinePoint:(CGPoint)point {
    NSLog(@"Click on line %f, %f",point.x, point.y);
}

```


## License

This code is distributed under the terms and conditions of the [MIT license](LICENSE).

## SpecialThanks

[@lexrus](http://twitter.com/lexrus)  CocoaPods Spec

