# Android Interview Guide

## Behavioral Interview

Describe one of your past Android projects.
- What were some of the major challenges you encountered?
- How did you overcome those challenges?
- What do you do when you get stuck?
- What is your approach to solving a problem you don't know the answer to?

## Technical Interview

Click on any of the questions to see the solutions!

#### Activity Lifecycle
<ul>

    <li>
        <details>
            <summary>What is an Activity?</summary>
            <a href="solutions/activity.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>List all of the methods that make up the Activity Lifecycle.</summary>
            <a href="solutions/activity_lifecycle.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>When is `onPause()` called?</summary>
            <a href="solutions/activity_on_pause.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>When is `onStop()` called?</summary>
            <a href="solutions/activity_on_stop.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>When should we save data from our Activity?</summary>
            <a href="solutions/activity_save_data.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>Is there a situation where  `onStop()` could not be called? If so, what is it?</summary>
            <a href="solutions/activity_on_stop_not_called.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>In what lifecycle method would I clean up any significant resources (Thread, Bitmaps, etc.) in my Activity?</summary>
            <a href="solutions/activity_cleanup_resources.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>What happens on orientation change (screen rotation)?</summary>
            <a href="solutions/activity_orientation_change.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
</ul>


#### Services

<ul>
    <li>
        <details>
            <summary>I needed to do something outside of the activity lifecycle. It needs to run across multiple activities. How would I do that?</summary>
            <a href="solutions/service_use_case.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>What do you know about service Lifecycle?</summary>
            <a href="solutions/service_lifecycle.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>What types of services are there?</summary>
            <a href="solutions/service_types.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>Whats the difference between starting a service and binding to a service?</summary>
            <a href="solutions/service_start_vs_bind.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>How does a bounded service work?</summary>
            <a href="solutions/service_bound.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>How do you stop both types services?</summary>
            <a href="solutions/service_stop.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    
    <li>
        <details>
            <summary>What are some of the drawbacks or limitations of using a Service? How would I get around them?</summary>
            <a href="solutions/service_drawbacks.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
</ul>

#### Concurrency 
- How would we perform concurrent operations on the Android platform?
- Are you familiar with concurrency (multi-threading) on Android?
- What are some drawbacks of AsyncTasks?
- If we wanted to download up to 5 images at the same time, could we do that with one AsyncTask? Why not?
- How would I download 5 images at the same time?
- Do you know of any other ways we can perform concurrent operations?

#### UI
<ul>
    <li>
        <details>
            <summary>What are some of the default layouts that are given to us by the Android Framework?</summary>
            <a href="solutions/default_layouts.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    <li>
        <details>
            <summary>What could you do with layouts that could lead to poor performance(stuttering)?</summary>
            <a href="solutions/layout_stuttering.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    <li>
        <details>
            <summary>What makes a RelativeLayout more expensive than other layouts?</summary>
            <a href="solutions/relative_layout.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    <li>
        <details>
            <summary>What is a RecyclerView? What are some advantages of RecyclerView over alternatives like ListView?</summary>
            <a href="solutions/recyclerview_advantages.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    <li>
        <details>
            <summary>Can you name some of the key concepts of Google's Material Design guidelines?</summary>
            <a href="solutions/material_design_concepts.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
</ul>

#### Fragments
- What is a Fragment? Why would I use one?
- What is a static fragment? Why would I use one?
- What is a dynamic fragment? Why would I use one?
- How can I communicate with my activity from a Fragment?

#### Other general Android Questions
<ul>
    <li>
        <details>
            <summary>What are some different ways you can store data on Android?</summary>
            <a href="solutions/android_storage.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
        <li>
        <details>
            <summary>What are some of the important functions of the AndroidManifest.xml?</summary>
            <a href="solutions/android_manifest.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
    <li>
        <details>
            <summary>Describe three reasons you would use an Intent. What is an explicit vs. implicit intent?</summary>
            <a href="solutions/intent.md">&emsp;&emsp; Click here for solution</a>.
        </details>
    </li>
</ul>






