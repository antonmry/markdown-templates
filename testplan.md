# App Master Test Plan

What is this app? 30K ft. view. Very high level

## Document Usage Guide

### Introduction

This is where the project mission statement goes. If you don't have one from
outside, write your own. Provide an overview of the plan in terms of what the
particular project covers. You may briefly mention items such as limitations in
resources and budgets, the scope of testing and how other activities such as
reviews are related. This is just a summary, so keep things short.

### Responsibilities

Provide details of who has the responsibility of delivering different parts of
the test plan. Name names. List specific parts of the *testing*.

### Roles

Give a low down of who is doing what with the project *outside* the scope of
testing. Name names. List titles and departments, maybe even contact data.

### Philosophy

The overarching testing paradigm if that wasn't covered elsewhere.

### Assumptions

Testing assumptions we will be making. This probably includes dependencies and
testability features.

### Staffing and training needs

Identify the people and skills needed to deliver the plan.

### Deliverables

Expected items from working through this guide. This may include bug reports,
updates to the guide itself. Identify what should be delivered as part of this
plan including documentation, pass/fail reports, test cases, session-based test
management reports, performance tracking, customer-facing documents, etc.
Everything that will be turned over to another party.

### Environmental needs

Are there any special requirements for these tests. You may want to consider
things like special hardware, test data or restriction to any system during
testing. This may include dependencies or other items like CI/CD,
infrastructure, test lab access, cloud hosting, etc.

### Testing tasks

Outline what functional tasks are required with exception to the actual testing.
You may want to consider equipment set up along with any administrative tasks to
account for tester time not spent in test.

### Suspension criteria and resumption requirements

State in what circumstances to stop and restart the test. Define clearly.
Perhaps BVT smoke testing invalidates a test session, for example. Or pre-release
checklists with a non-zero amount of failures block the release.

### Item pass/fail criteria

State the acceptable pass / fail criteria. This can be some general criteria or
at the individual test case level. Some tests failing might be expected during
development.

### Approach

Outline the overall test strategy for this plan, identifying the test process
and rules that will be followed. You may also want to include any information
about tools, software, or hardware that will be used.

### Test items

List the items that will be tested. This could be a software product, system or
website. This is the overarching thing we are testing.

### Features to be tested

List the *features* that will be tested and are within the scope of this test
plan. This is *broad* don't worry about every tiny feature or subfeature. Those
will be covered later.

### Features not to be tested

List the features/requirements that will not be tested and are outside of the
scope of this test plan.

### Resources

Project setup and links. Oracles. External tools, test accounts, mock data,
knowledge bases. etc.

### Schedule

Provide a realistic estimate of the time required. Think about sections, tasks,
subsections, regression testing and publish intervals. This should map to an
existing project plan.

### Risks and contingencies

Identify any known areas that are high risk and may cause delays or disruptions.

### Approvals & Completions

Identify who can approve the completion and what that may mean.

### General Test Coverage

Where is each approach outside of this document covered? Unit testing. Smoke
testing.

### Document Maintenance

Who how where and when regarding this document. Dropbox, DVCS, wiki, confluence,
alongside the project source?

___

## Testing

**Plans, Areas, Methods, Features and Checklists** Testing the app from 10K ft.
to 0.01 mm away. This is where we start to get our hands dirty.

### Smoke Tests

Identify and attempt to *automate* the core functions that need to pass in order
for a build to be ready for testing. Perhaps passing unit tests first. Perhaps
just confirming the build can open and close. Perhaps any automated tests you
have laying around. Figure this out and attach it to the build process.

### Unit Testing

Describe any unit testing in the project and how it relates to document user
here. Is it attached to the CI server? Is it something the developer only runs
locally before they push or merge? What kind of coverage is there between the
code and the unit tests. Is only one part or developer involved, etc.

### Automated Testing

Give a census of all automated tests and point to instructions for maintenance
or additions. This document is a tool of a black box tester and while they may
use tools they are not expected to create and maintain sets of tools for the
project.

### Basic CRUD Testing

Create Read Update Delete. Perhaps this is also automated and attached to the
build process. Write a script that will do all in a swoop and also check each
action.

### Hardware Testing

Max and minimum supported hardware. Document and test against. CPU, RAM, et al.
Make sure to do a check on Virtual Machines (faked hardware) and graphics
drivers/cards. You should attempt to do the majority of your testing on a low-end
device and have a high-end device at the ready for reproduction of anomalies.

### Input Method Testing

Keyboard, touchscreen, trackpad, voice, pen, foreign language devices, assistive
devices, Bluetooth enabled devices, other supported peripherals. Log them and use
them in scenarios and domain test cases.

### Bounds Testing

Wedging for fun and for profit. Combine known quicktests with domain testing to
specifically do boundary analysis testing.

### Feature Testing

Map each application-specific feature hierarchically and verify performs as
expected. This is a mass census by way of a touring heuristic and then writing
tests against the items in both happy path and risk-focused test cases.

### UI Testing

Use a UI touring heuristic to log any UI specific tests and suspect scenarios
meant to tickle UI defects. Think Layouts. Sections. Buttons. etc. Define views
and pages and their respective parts. Cover animations & transitions here. Get
flows and storyboards so you have known outcomes.

### UX and Usability Testing

Layouts. Sections. Buttons. etc. Define views and pages and their respective
parts. Cover animations & transitions here. Get flows and storyboards so you
have known outcomes.

### Screens Testing

Resolution, screen size, pixel density, window size, responsiveness,
orientations, external screens, etc.

### Search Testing

Searching, finding, highlighting and all things related to search within your
application. From performance to results.

### Preferences Testing

User configurable application preferences. In the application and behind the
scenes. Log and change and devise test cases that may bring defects to the
forefront.

### Communication & Dialogs Testing

Interactivity, clarity, spelling, context, behavior. Feedback.

### Menus, Key Equivalent Testing

Checking each and every menu item, contextual menu item, each keyboard shortcut,
and all variations and states.

### Configuration Testing

Test each and every internal setting and the features they touch.

### Internationalization Testing

How does it handle another locale or language setting? And inputs?

### Localization Testing

Is the app localized? How does it hold up? Do UI elements support varying string
lengths? Does the app go into the correct mode at the correct time? How have the
strings been validated?

### Claims Testing

Review marketing materials and ensure that each thing is true. Review release
notes and validate each new entry is accurate for current build state.

### Beta Testing

Exploratory black box testing from non-stakeholders. This may be a robust
external group that your CS team governs or it could just be throwing builds to
your team ad hoc. Outlay your plans here.

### Documentation Testing

Help guide, about page, get started – any piece of written stuff that is
available in-application.

### Security Testing

Buffer overruns? SQL injection? Gatekeeper, signing, sandboxing, injecting,
licensing, etc. OWASP Top 10 is a good starting point but it shouldn't be the
whole show.

### Binaries Testing

Inspect the application bundle in the finder as deep as you are able. Do the same
in Xcode and with any known inspection tools you have. Pass a `strings` over it.
Try to fiddle with the innards and see if there is anything inappropriate

### Risk Testing

All points where data is saved and changes are executed. Make a list and test
cases for each and every area.

### Upgrade & Installation Testing

Installs, updates, and upgrades. Cover un-installations here.

### Analytics Testing

Any analytics support and confirmation in test/prod envs. Be sure to validate
your internal use isn't poisoning numbers.

### Third Party Tools Testing

Store, Sparkle, TestFlight, frameworks, advertisement libraries, etc.

### External Obligations Testing

Are you contractually obligated to show a client logo in certain areas? Do you
need to have license credits in the about page? Are you using the correct social
media logos?

### Debug Testing

Have you left any debug nonsense laying around? Do your logs get shuffled off to
an email? Do you point to a temporary server? Is the console spewing things it
should not? Have a developer help you audit these items.

### First Run Experience Testing

Welcome screens, EULAs, data migrations, prefs, licensing, updates, system
checks, how-to guides, use reporting, configuration, walkthroughs, anything and
everything tied to the first run of a fresh install. The first run of an update.

### Interoperability Testing

Interoperability between other apps or OS’s or services.

### Modes and States Testing

Dirty environs, messed up settings, sleep mode, safe mode, restarts, etc.

### Friendly Neighbor Testing

Determine apps and tools that users may use with your application and make sure
they play nice.

### Network Testing

Configs, failures, and events. Get busy with the Network link conditioner. Jam a
proxy into the mix. Cover network on first launch and relaunch issues. Yank the
internet. Strangle your bandwidth.

### Project Legacy Testing

Review bug reports from previous versions and beta tests from early incarnations.

### Accessibility Testing

Mouse-less, sight-less, sound-less, colorblind, enlarged text, inverted color,
zoom view. is everything perceivable, operable, understandable, robust
experience? Truly sightless VO testing, etc.

### Stress & Performance Testing

Load, endurance, boundaries, interruptions, starvation, etc. Establish numbers
and then push them.

### Chaos Monkey Testing

Research Netflix's Chaos Monkey and take your cue from the monkey and go
nutzo-smasho on some software. You will find a lot of timing bugs this way and
cases where errors are shown are a trove of bugs.

### Scenario Testing

Develop use cases and stories. Extract examples from the team, from the support
queue and our potential customers. Your stakeholders from all points of entry.
As a _$USER_ I need to _$ACTION_ so that I can _$RESULT_.

### Internal Stakeholders Testing

Pick a team member or area and ask an interested team member what *they* would
like tested or if they have any particular concerns about their areas.

### Support Advocacy Testing

Identify weak points in prior versions that have caused support load and tackle
these here. Try to identify weak points that have carried over and any new ones.
Beta & exploratory ad hoc testing are your friends here.

### Mockups & Design Track Testing

Are we in line with published mock-ups? Has the designed diverged? Create test
cases that can flow with the constant change of direction. This is more back-end
stuff that you should do with the aid of design & dev, not general UI/UX testing.

### Competitor Testing

Identify existing competitors. Run actions in their software that we can
accomplish in ours. Compare and contrast and report findings. Review their
release notes and support FAQs for test ideas.

### Core Values Testing

Refer to the project mission statement. Refer to software values ethos of the
product owner. Take specific statements and create test cases against them.

### Regression Testing

Performance vs last public release. Versus latest beta, alpha, build, update,
etc.

### Personal Testing

Identify yourself as a stakeholder, what needs to be tested by you and for you?
What are areas you think no one is paying attention to? Document and share and
test those items. You have a passion for software quality and are a champion for
the product customer, right? What are you doing above and beyond to fight for the
end user?
