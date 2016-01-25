
---

| Title | Type | Duration | Name | City |
| --- | --- | --- | --- | --- |
| Activity Lifecycle | Lab | "1:00" | James Davis | NYC |

---  
# Activity Lifecycle Lab

## Introduction

Below, you will find three scenarios, and questions following each one.

To the best of your ability, answer the questions **in english**, not in code.

Below the scenarios, you will find a few questions. Answer those however you'd like.

Answer the questions by editing this readme, pushing your changes to your forked repo, and making a pull request.

## Exercise  


####Scenario 1:

Let’s say you made a To Do list app, where you can add things to a list and cross them off. You decide to cross some items off the list and mark them as complete.

When you rotate the device, the things you marked as complete are no longer crossed off.

**Question**: Why did this happen?
<br />Answer:
Rotation of the device destroys the current activity (screen) thus leaving the previous state unsaved.

**Question**: How do you fix this issue?
<br />Answer:
You would need to save the current state before the rotation occurs and resume on rotation.


####Scenario 2:

The Amazon Kindle Android app allows you to open and read eBooks. You discovered a bug! You opened a book, and read it from the beginning up to page 68. Then, you left the app and closed it completely so you can do other things.

When you opened the app again, and opened the book, it started from page 1 (and not page 68 where you left off)!

**Question**: How would you fix this issue?
<br />**Answer**:
Each page is an int value that should be stored in the onPause method to the SharedPreferences object in order to restore the original page the user left off later.  Access to the onResume to getInteger method for the SharedPreferences should be used.

onSaveInstanceState would only save settings while the program is still active in the background of the device.  Data is gone when the application is terminated.

SharedPreferences would persist the data even after the program is terminated as it is stored locally.

####Scenario 3:

Facebook for Android added a feature last year where, if you started writing a comment on someone’s post and decided not to do so, the app would save a draft of it just in case you changed your mind.

Take this scenario. On a post on Facebook, you click the “comment” button (which opens a new CommentActivity). You start writing a comment, and then change your mind by pressing the back key (which closes the CommentActivity). You click on the “comment” button again, and in the newly-opened CommentActivity, the comment you were writing is still there.

**Question**: How would you implement this feature? Be specific; what lifecycle methods would you use in CommentActivity, and what techniques would you use?
<br />**Answer**:

You would utilize SharedPreferences to save the typed draft by the user onPause method for the data to be stored in the activity.  onResume, the data would be reinvoked and would be displayed on view.




In your own words…
==================

**Question**: What are the methods of the Activity Lifecycle?
<br />**Answer**: 

onCreate();
onStart();
onResume();
<App Running>
onPause();
onStop();
onDestory();

**Question**: What order are the methods called?
<br />**Answer**: 
onCreate();
onStart();
onResume();
<App Running>
onPause();
onStop();
onDestory();


**Question**: What is a bundle?
<br />**Answer**: 
Data container, stores data

**Question**: How do you get the Shared Preferences of an app?
<br />**Answer**:
Declare a new SharedPreferences object

SharedPreferences sharedPref = getSharedPreferences();

SharedPreferences.Editor editor = sharedPref.edit():
//puts data
editor.put();
//commit data
editor.commit();
//to edit SharedPreferences
