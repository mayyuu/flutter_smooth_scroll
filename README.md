# smooth_scroll_web

A simple package, that helps the feel of the Scrollable widgets.

# About me 
You can find out everything about the creation of this package, how it works by opening this link. 
https://hobbister.com/2020/11/17/smooth-scrolling-with-flutter-web/
It would be very appriciated.


# Getting started
The package should only be used for Flutter Web and on the desktop version of the site, while the mobile version of Flutter is doing a really good job of scrolling, with really great performance, It cannot be said for the mouse wheel scrolling.

You can use the package with any Scrollable widget, but you have to set its physics to NeverScrollableScrollPhysics(), because it is the only way to deactivate the default scrolling and we need complete control over the scrolling.


# Without and With SmoothScrollWeb

![smoothless](https://gitlab.com/dezso15/smoothscrollweb/-/raw/master/smoothless.gif)
![smooth](https://gitlab.com/dezso15/smoothscrollweb/-/raw/master/smooth.gif)

Bluring is due to the movement and the gif's poor quality.

# Example
```dart
@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("SmoothScroll Example"),
      ),
      body: SmoothScrollWeb(
        child: _getChild(),
        controller: controller,
      ),
    );
  }

  Widget _getChild() {
    return Container(
      height: 1000,
      child: ListView(
        physics: NeverScrollableScrollPhysics(),
        controller: controller,
        children: [
          for (int i = 0; i < 100; i++)
            Container(
              height: 60,
              color: RandomColor.generate(),
            ),
        ],
      ),
    );
  }
