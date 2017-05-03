# ESaaS Engagements Tracker

The goal of this currently bare-bones app, thrown together by Armando
Fox, is to do continuous tracking over time of customer apps developed
by the "ESaaS ecosystem" around [UC Berkeley CS169 Software
Engineering](https://cs169.saas-class.org).

Since we have had many repeat customers who come back in subsequent
semesters to have a new student cohort enhance an existing app, this
system will track an app's current status over its lifetime as it is
handed off from cohort to cohort.

The main models are:

* App: a deployable Web app.  An app's status may be:
  * `inactive`: not deployed, and/or customer not actively using;
  dormant
  * `development`: in active development, whether or not deployed in
  production
  * `maintenance`: deployed in production, not currently in active development
* Org: a customer organization for whom the app was developed
* User: various subcategories, including developer (e.g. student), coach
(mentor, GSI), customer contact.  Also a principal for authentication,
though as of this writing there's no login/auth support.
* Coaching org: an "organization" whose main function is to provide
mentoring/coaching to students building apps.  E.g., "UCB CS169 Fall 17"
is an org, as is "[AgileVentures](https://agileventures.org)", and so
on.  I would propose that each offering of CS169 be its own org, so we
can track engagements accurately.

An **engagement** is a period of time over which a coach interacts with
developer(s) to work on an app.  During that time, the app is in
`development` status.

After the engagement ends, the app is either in `maintenance` status
(customer is using it; app may be enhanced in future) or `inactive`
(customer not using it, because it doesn't meet their needs enough to be
usable). 

At any given time every app is always part of an engagement, so
engagements have a start date but no end date; an engagement ends when
the app transitions into another engagement.

So for example, an app that is developed in Spring 2017, used by the
customer over the summer, and picked up by another cohort for
enhancements in Fall 2017, might have these engagements:

| Status      | Start date | Coaching org  | Coach      |
|:----------: | :-:        | :-:           | :-:        |
| development | 1/15/2017  | CS169 S'17    | Tony Lee   |
| maintenance | 5/5/2017   | AgileVentures | Sam Joseph |
| development | 8/23/2017  | CS169 F'17    | An Ju      |

# Why?

The goal is to have a robust ecosystem that eventually encompasses not
only UCB CS169 but its offshoots: the AgileVentures volunteer-developer
corps, ESaaS-like courses at other schools (Texas A&M now emulates UCB's
approach and builds software for local nonprofits), etc.

When a new course offering starts, or when a non-course org is looking
to source projects, they can look here to find apps in need of
enhancement; if greenfield apps are built, they can be registered here
so that future dev teams can pick up and enhance them.

# High priority feature list

0. SSO-only login: GitHub for devs/coaches, Google or Facebook or
LinkedIn for customer contacts
0. Add/edit/manage users, including signup using SSO
0. Add user contact info and a way to track user meeting notes
0. Add/edit engagements
