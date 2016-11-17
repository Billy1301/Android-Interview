## Describe three reasons you would use an intent. What is an explicit vs. implicit intent?

You might use an intent to...

1. To start an Activity

2. To start a Service

3. To deliver a Broadcast

An *explicit* intent specifies the component to be started by name. An *implicit* intent does not - instead it declares a general action to perform, which allows a component from another app to handle it. As an example, if you want to show the user a location on a map, you can use an *implicit* intent to request that another capable app show a specified location on a map.

[[Android Developer Reference]](https://developer.android.com/guide/components/intents-filters.html)
