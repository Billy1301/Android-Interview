##What are some of the important functions of the AndroidManifest.xml?

There are many notable functions of the Manifest file. These include:

* Naming the Java package for the application. This uniquely identifies the application.

* Declares which permissions the application must have in order to access protected parts of the API and interact with other applications. It also declares the permissions that others are required to have in order to interact with the application's components.

* It declares the minimum level of the Android API that the application requires.

* Contains a list of the libraries that the application uses.

* Describes the components of the application, including activities, services, broadcast receivers, and content providers, and names the classes that implement each of the components, and publishes their capabilities, and under what conditions they are allowed to be launched. 

* Determines which processes will host application components.

* It can list the Instrumentation classes that provide profiling and other information as the application is running. These declarations are present in the manifest only while the application is being developed and tested; they're removed before the application is published.


[[Android Developer Reference]](https://developer.android.com/guide/topics/manifest/manifest-intro.html)
