## Caching

Most of the data on WaniKani doesn't change that often, so long-lived caches or more permanent stores that are periodically updated can eliminate a lot of time-consuming requests and help with offline functionality, if that's something you're after.

Here are a few recommendations that might influence what you cache and how long you keep it around:

* Cache [subjects](#subjects) as aggressively as possible. They aren't very frequently updated, and you'll probably need to access them frequently. They're the object that ties together assignments, review statistics, and study materials.
* Reviews and resets are never changed once recorded, but reviews are created frequently. You can put these two in long-term storage if you need them.
* Assignments, review statistics, and study materials have moderate levels of updates. When a user levels up or passes a a subject, there might be a small flurry of activity with new assignments being created and existing records being updated. As an assignment gets further and further along in the SRS stages, those updates will become less and less frequent.
* The summary report changes every hour. Caching the results of this request might help with offline activity, but the data changes, well, every hour.
* The user endpoint isn't updated a ton, but when it does, it's going to be pretty important to capture.

Do take note any of the above recommendations may become outdated, but we will try out best to communicate these changes.

Caching is always tricky business. When do you expire it? How do you refresh it? Who's in charge of it?

We've done a couple things to try and help with a couple of the problems around caching. The first is to support [conditional requests](#conditional-requests), which lets us quickly tell you that a record hasn't changed since you got it last. The second is to give you tools to [get only the updated or new records after any point in time](#leveraging-the-updated_after-code-filter), letting you easily refresh your local data caches and stores without having to parse _all_ the records.
