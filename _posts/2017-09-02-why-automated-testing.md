---
title:  "Why automated testing?"
date:   2017-09-02 12:16:30
categories: [testing, agile, best-practices]
tags: [testing, agile, best-practices]
---
Automated testing is a great way to ensure software quality. The TDD (Test driven development) leads the developers to create simple and maintainable code while BDD (Behavior Driven Development) is responsible to test the connected parts of the software, that is, it's behavior or domain.

Both methods can reduce the incidence of bugs in a production environment and saves a lot of money and time over manual testing.

## What is TDD?

TDD is basically a process of writing automated tests to ensure that code works before write the implementation.

There exists 3 main steps which is red, green and refactor. The developer writes the test and runs it before create the implementation (**red**), then writes the implementation and runs it again until it pass (**green**). if needed, the developer can refactory the code (**refactor**). These cycle should be repeated as the developer builds the software.

## What is BDD?

BDD is an Agile technique of writing test scenarios defined by business requirements which ensure the software behaves as expected.

The BDD encourages collaboration between developers, QA and non-technical or business participants in a software project. Let's see how it should look like using [cucumber](https://github.com/cucumber/cucumber-ruby):

```cucumber
Feature: Working hours approval
  As a manager I should be able to approve the working hours of the employees of my team.

Background:
  Given I'm logged in as manager user
    And the employee "John" have "3" working hour records waiting for approval

Scenario: Manager should be able to see the pending approval working hours of my team
  Given I click on "Time tracking" on menu
   When I click on "Pending approvals" link
   Then I should see "3" records marked as "pending" being "John" the author
```

Note that the feature can be used as a documentation and have the pre-conditions (**given**), actions (**when**) and assertions (**then**), so anyone can quickly understand whats the behavior of the software.


## Why you should start using it

If you want to ensure quality on your application, you should have manual testing. But there are some advantages of automated testing that can help you achieve your goals and improve your ROI:

**Regression test in minutes**

Once the test is executed by a machine, you'll be able to test all the application in a few minutes. Then it can save you a lot of time to focus in other activities.

**Can be used as documentation**

The test suite can help new members of the team to understand the application behavior.

**Code refactoring will be much faster and easier**

If your application is well covered by tests you can change everything and quickly ensure you didn't change its behavior.

**Turns the application more reliable**

It removes the human error by performing boring and repetitive tests.

**Your team may be smaller**

You do not need multiple people testing the software manually if you have a test engineer.

**Early bug detection**

Automation help developers to discover more bugs in the early phases of software development and prevent some strange or wrong behavior in a production environment.

## Conclusion

Test automation is not a silver bullet, but it is a strong ally and can bring you more profit than injury and helps your team to not commit some basic errors and reduces the bug insidence by making your team more profitable and smaller.
