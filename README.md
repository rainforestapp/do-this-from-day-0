do-this-from-day-0
==================

Stuff you should do from day 0, to minimize technical debt.

## Access Management

- Users must be distinct from accounts:
  - Accounts handle billing, authorization, ownership
  - Users log in, belong to accounts through memberships, optionally have variable permissions

![](https://raw.githubusercontent.com/rainforestapp/do-this-from-day-0/master/assets/Auth%20UML.png)

### Remarks

* Users have potentially multiple email addresses. I want notifications for my work account to go to my work email, and personal account to my personal email. GitHub does this, but several others (TravisCI) do not.
* Accounts belong to a parent account. The top company is the developer of the app, and engineers belong to that account. Authorization at a parent account permits access at the lower accounts, allowing developers to `sudo` at any account. This also allows for resellers to have control over aspects of lower account. The account hierarchy ends up being very shallow (2-3 levels at most) and very wide.
* Users have multiple API Tokens, similar to google application-specific passwords, or AWS Access Keys. They're one-time viewable and easily revokable.


## Notifications

- Everyone needs a low-priority, async messaging center
  - Something happened offline in the background and you need to let the user know
  - Persistent message list, shows the unread ones on login
  - Bar at the top of the screen, pulled from a queue
