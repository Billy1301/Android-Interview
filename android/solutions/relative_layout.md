##What makes a RelativeLayout more expensive than other layouts?

A relative layout positions elements relative to others horizontally and vertically. It has to do two measure passes, whereas Linear layouts only need to do one; Therefore, relative layouts are more expensive than LinearLayouts, which are more expensive than FrameLayouts.

Useful Resource:

[Popular SO post](http://stackoverflow.com/questions/4069037/android-is-a-relativelayout-more-expensive-than-a-linearlayout) with some good video lectures on the subject
