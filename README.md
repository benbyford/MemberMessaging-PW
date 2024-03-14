# MemberMessaging-PW

Member Messaging module for Processwire - this is a commercial module that can be purchased here: [https://benjaminbyford.gumroad.com/l/membermessaging](https://benjaminbyford.gumroad.com/l/membermessaging)

This is a module for Processwire CMS to enable you to easily setup a messaging system for your users. Allow your website users to message other users on the site given a user name or similar information.

Module uses the notions of threads, messages and users to describe the message relationship. A thread is a page storing n messages including: time, created by user and message text, the users in the thread, which users have unread messages in this thread, whether messages are encrypted (and it's salt). User pages have a list of all threads they are apart.

In your templates you can add: a compose message form, threads and their messages, thread reply forms, message and threads counts, as well as delete and delete all messages. You can view messages in the admin (unless encrypted set to True) and view message stats and module usage in admin page Members.

More information see the PW forum post or contact me [here](hello@benbyford.com).

Example usage - new thread form, thread and messages with reply form

## Public functions:

```
// get module
$mm = $modules->getModule("MembersMessaging");

// get count of total messages for this user
$msgThreadCount = $mm->msgThreadCount();

// count of unread message threads - must be called before getUserMessages
$unreadMsgsCount = $mm->countUnreadThreads();

// show message form
$composeMessage = $mm->composeMessage();

// get all messsages with reply forms
$userMessages = $mm->getUserMessages();

//render most of the above
$exe = $mm->execute();

// if you want to delete all message pages and message id's saved to users, then call flushMessages()
$mm->flushMessages();
```


## Basic usage:

```
// basic usage doing most of the above
$mm = $modules->getModule("MembersMessaging");
echo $mm->execute();

// include example js and css implementation to help you get up and running with sending messages
echo $mm->js();
echo $mm->css();
```
