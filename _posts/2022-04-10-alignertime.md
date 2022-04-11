---
layout: post
title: "A Better App for Invisalign"
tags: programming swift
carousels:
 - images:
   - image: ../images/posts/alignertime/SetupScreens/welcomeViewPermissions.png
   - image: ../images/posts/alignertime/SetupScreens/welcomeView.png
   - image: ../images/posts/alignertime/SetupScreens/q1View.png
   - image: ../images/posts/alignertime/SetupScreens/q2View.png
   - image: ../images/posts/alignertime/SetupScreens/q3View.png
   - image: ../images/posts/alignertime/SetupScreens/q4View.png
   - image: ../images/posts/alignertime/SetupScreens/q5View.png
   - image: ../images/posts/alignertime/SetupScreens/finishView.png
 - images:
   - image: ../images/posts/alignertime/TimerScreen/firstView.png
   - image: ../images/posts/alignertime/TimerScreen/trayOutView.png
   - image: ../images/posts/alignertime/TimerScreen/trayBackInView.png
   - image: ../images/posts/alignertime/TimerScreen/setReminderView.png
 - images:
   - image: ../images/posts/alignertime/HistoryScreen/dayViewEmpty.png
   - image: ../images/posts/alignertime/HistoryScreen/dayView.png
   - image: ../images/posts/alignertime/HistoryScreen/editBreaksView.png
   - image: ../images/posts/alignertime/HistoryScreen/weekView.png
   - image: ../images/posts/alignertime/HistoryScreen/monthView.png
 - images:
   - image: ../images/posts/alignertime/ProgressScreen/emptyView.png
   - image: ../images/posts/alignertime/ProgressScreen/allPhotosView.png
   - image: ../images/posts/alignertime/ProgressScreen/compareView.png
 - images:
   - image: ../images/posts/alignertime/SetupScreens/overviewView.png
---

In the spring of 2021 I started Invisalign, and while the treatment itself has been a wonderful experience, the app that Invisalign provides leaves
much to be desired in both usability and aesthetics (though, I admit in the last year or so they have made some pretty good improvements).
During the months I've been doing the treatment, I had been wanting to learn another programming
language to spice up a bit of a dull point in my software development career.

I have done some mobile development in the past [Translite](https://kristaboone.github.io/translite/), and other side projects,
but they had all been for Android. So I set out to learn a new development platform, get familiar with a new IDE,
and learn a new language- Swift. I had a great time learning Swift through [this course on Udemy](https://www.udemy.com/course/ios-13-app-development-bootcamp/).
(It's also a great course to generally learn programming, but if you're familiar with the basics you can breeze through those introductory lessons.)

When I finished the course I wanted to build a 'capstone' of sorts to demonstrate what I had learned about iOS app design and development.
Alignertime is the product of this capstone.

# Alignertime

Alignertime is an iOS app that helps you stay on track with your Invisalign treatment. When you are doing an Invisalign treatment, it's recommended
to wear your trays for the majority of the day, taking breaks only when you eat meals- sometimes you forget to put your trays back in or you
underestimate how long you've had them out. Not wearing the trays for the recommended time could mean a longer treatment time, or if rushed, having to
redo the treatment again.

## Methodology

As someone who likes a well laid-out plan for developing software, I set up a personal Jira project and broke the app up into epics,
user stories, and subtasks. Whenever I had some time, I would tackle some of the subtasks until the project was finished.
The epics for the project were:

 * Allow user to time tray in/out time for a day
 * Display history of user's wear time over a selected time period (day, week, month)
 * Allow user to take and store progress images
 * Display progress images to the user in a useful way
 * Allow user to input treatment plan information into system

Once the high-level goals for development were set, I mocked up the app UI using a program called [Sketch](https://www.sketch.com/).
While working through this, I built out a user flow Diagram using draw.io to identify what screens would be needed based on each of the
functional requirements and how the user would navigate between them.

## Implementation

The app has a questionnaire when you get started to set up your treatment and 4 main views- the Timer View, History View, Progress View, and Profile View.

### Welcome Questionnaire

The welcome questionnaire gets information about the user's treatment plan when they first open the app.

{% include carousel.html height="600" unit="px" duration="5" number="1" %}

### Timer View

The timer view is probably the most used view of the app. It provides a large timer that at the start of each day, will show the total amount of
'break time' or allowed time that the user should have their trays out during the day. The time here will be 24hours minus their goal wear hours set
up in the welcome questionnaire.

{% include carousel.html height="600" unit="px" duration=5 number="2" %}

The user can start the timer one of two ways. The first way is by pressing the tray in/out segmented control. When the user marks that the trays are
out, the timer will start counting down, updating the UI every second with the current time. Another way is to press and hold on the alarm button in 
the bottom right corner of the timer- this will set an alarm to go off and notify the user that it's time to put their trays in after their selected
amount of time.

Ideally, by the end of the day, the timer reads 0 or another positive time, indicating that they wore their trays for their goal time for the day.
If they go over, the timer text will turn red, indicating they did not meet their goal for the day.

The information in this view is stored in a database and recalled to be displayed in the History View.

### History View

The history view displays the wear history for the user for a day, a week, or a month.
In the day history view, the user can see all the breaks they've taken in that particular day and edit/remove them. The week and month views
show the history for the week and month, repectively. If the user has not hit their goal for the day/week/month the wear time or average wear
will be displayed in orange, otherwise it will be in blue text.

{% include carousel.html height="600" unit="px" duration=5 number="3" %}

### Progress View

The progress view lets users take and/or upload images of their smile to create a progress photos gallery. There is also a slider
view to compare the first and latest images of their smile. 

{% include carousel.html height="600" unit="px" duration=5 number="4" %}

### Profile View

The profile view gives the user an overview of which tray they are on, when they change trays, and how long they have left in their treatment.
It also allows the user to update any of the treatment settings set up in the initial questionnaire.

{% include carousel.html height="600" unit="px" duration=5 number="5" %}

## Conclusion

Application design and development (for either mobile or desktop) is something I really enjoy- building something new from scratch that is 
useful to at least one person. If you'd like access to the app, you can reach out to me at the email listed here on my website.
