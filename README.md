do-this-from-day-0
==================

Stuff you should do from day 0, to minimize technical debt.

## Access Management

- Users must be distinct from accounts:
  - Accounts handle billing, authorization, ownership
  - Users log in, belong to accounts through memberships, optionally have variable permissions

## Notifications

- Everyone needs a low-priority, async messaging center
  - Something happened offline in the background and you need to let the user know
  - Persistent message list, shows the unread ones on login
  - Bar at the top of the screen, pulled from a queue
