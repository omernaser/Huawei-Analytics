![enter image description here](https://raw.githubusercontent.com/omernaser/Huawei-MAP/master/huaweiicon.png)
## Xamarin.Android.HMSAnalytics

**Introduction**
AppGallery Connect is dedicated to providing one-stop services for app creation, development, distribution, operations, and engagement, and building a smart app ecosystem for all scenarios.

HUAWEI Analytics Kit provides advanced analytics capabilities for AppGallery Connect, helping developers implement closed-loop management driven by data analytics, ranging from business insights to product improvements and operations execution. The Analytics Kit collects user behavior events and user attributes to help developers clearly understand user behavior models, thereby enabling user insights, product optimization, and data analysis-driven operations.

### Setup

-   Available on NuGet:  [[[https://www.nuget.org/packages/Xamarin.Android.HMSAnalytics/](https://www.nuget.org/packages/Xamarin.Android.HMSAnalytics/))][![NuGet](https://camo.githubusercontent.com/8a3005d7f8ce0d50737ec134a48480ad61bfa5b9/68747470733a2f2f696d672e736869656c64732e696f2f6e756765742f762f506c7567696e2e4669726562617365507573684e6f74696669636174696f6e2e7376673f6c6162656c3d4e75476574)](https://www.nuget.org/packages/Xamarin.Android.HMSPushKit/)
-   Install into your .NETStandard project and Client projects.
-   Please make sure you have Xamarin.Android.HMSAdditional and Xamarin.Android.HMSBase as a refernance

**Platform Support**
Xamarin.Android


**How To Use**
1. You should add these lines to your MainActivity.cs

>          var config = AGConnectServicesConfig.FromContext(this);
            config.OverlayWith(new HmsLazyInputStream(this));
            Com.Huawei.Agconnect.AGConnectInstance.Initialize(this);

2. You should add agconnect-services.json to the assets Folder 
refer to the following link to get it [https://developer.huawei.com/consumer/en/codelab/HMSAnalyticsKit/index.html#2](https://developer.huawei.com/consumer/en/codelab/HMSAnalyticsKit/index.html#2)
## Features

# Dashboard
The app overview centrally displays core metrics (such as new users and user activity) of the current app, and provides the entrances for event analysis and activity analysis, helping you quickly understand recent overall performance of your app.

# Event Analysis
HUAWEI Analytics Kit provides various event analysis functions and supports  [preset events](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/event_description#preset_events)  (including auto-collected events and predefined events) and custom events.

Reported event data is aggregated by event ID. You can view the event overview and event analysis details, such as the event trend and the distribution of models and operating system versions that are sources of events.

# User Analysis
User analysis includes new user analysis, active user analysis, and startup times analysis. By analyzing users, you can understand the user royalty of a product and set activeness promotion strategies accordingly

# User Lifecycle
User lifecycle refers to the entire process from the time when a user starts the app for the first time to that when the user leaves the app. The lifecycle of a user can be divided into the following phases:  **Beginner**,  **Growing**,  **Mature**,  **Inactive**, and  **Lost**.

Operations personnel can perform user steering and refined operations on users based on user lifecycle analysis to improve user activeness and retention and reduce user churn.

# User Behavior
Behavior analysis includes activity analysis, revisit analysis, and page analysis.

User activity is a key metric for product stickiness and health status. Through activity analysis, you can understand the dependency of users on your products.

In addition, you can analyze revisit users to understand the ability for operation campaigns or new product features to win back users.

By analyzing the access trend, access depth, and stay duration of different pages in an app, you can determine the importance of each page and provide data support for page optimization strategies.

# Attribution Analysis
Attribution analysis of in-app events measures the conversion contribution of to-be-attributed events (such as tapping a push message) to target conversion events (such as placing a purchase order). You can define target conversion events and to-be-attributed events, and select an attribution model to generate an attribution analysis report. The report helps evaluate the marketing channel conversion effect so that you can adjust your strategy in time.

An attribution model is a rule or a set of rules that determine how to assign sales and conversion contributions to contact points in the conversion path. For example, the Last event attribution model assigns 100% of contributions to the final contact point (that is, a tap) before sales or conversion, and the First event attribution model assigns 100% of contributions to the contact point that triggers the conversion path.

# Audience Analysis
An audience is a group of users who have common attributes and behavior. You can perform insight analysis on audiences to understand which users are more likely to be attracted by your products. You can also customize operations strategies for different audiences to improve user experience and operations efficiency.

# Path Analysis
Path analysis displays the behavior paths of users in apps and provides product managers and operations personnel with key data about user actions in apps and the process of leaving apps. For example, after a new version is released, users' recognition of new functions can be obtained through behavior path analysis. Alternatively, e-commerce operations personnel can use the path analysis function to obtain the churn rate of users in a certain step.

# Funnel Analysis
The funnel analysis supports comparison based on a specific indicator. Currently, user attribute comparison, audience comparison, and industry comparison are supported. For example, you can compare the funnel conversion rates of different device brands or perform drill-down analysis for industry categories.


# Retention Analysis
Retention is critical to app growth and operations. The retention rate represents users' continuous interest in products and is one of the main metrics for measuring the core value of products. Retention analysis helps you understand the continuous attractiveness of your product to users.

# Real-time Analysis
HUAWEI Analytics Kit displays the counts and proportions of the hottest events, event parameters, and parameter values in real time. Real-time analysis helps product managers and operations managers understand the effect of marketing and product improvement.

The real-time analysis report page provides the automatic refresh function. After this function is enabled, the page is automatically refreshed every minute. If the function is disabled, you need to click the refresh button to refresh the page.

# App Debugging
During app development, the product manager and technical team can cooperate with each other to perform the final debugging on data reporting, preventing tracing point omission and event attribute setting errors.

# App Version Analysis
The app version analysis report gives you a knowledge of the app adoption rate, interaction, and stability, helping you optimize the version policy.

# Meta Manage
You can manage events, user attributes, and pages in metadata management.

# Analysis Settings
You can manage settings for advanced analytics on this page.

## Sample Events:

![enter image description here](https://raw.githubusercontent.com/omernaser/Huawei-Analytics/master/Screenshot_20200520_144324_com.companyname.hms_map_demo.jpg)






## Reference


[https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3021001](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3021001)

[https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3021002](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/3021002)

[https://developer.huawei.com/consumer/en/hms/huawei-analyticskit](https://developer.huawei.com/consumer/en/hms/huawei-analyticskit)
