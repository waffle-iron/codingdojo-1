# Introduction
## TDD
* See [Wikipedia](https://en.wikipedia.org/wiki/Test-driven_development)

## BDD
* See [Wikipedia](https://en.wikipedia.org/wiki/Behavior-driven_development)

## Markdown
* See [Markdown Cheat Sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

```Markdown

 # Headline 1
 ## Headline 2
 ### Headline 3

 * dash

 ```code
```

## C++
* See [Wikibook (German)](https://de.wikibooks.org/wiki/C%2B%2B-Programmierung/_Inhaltsverzeichnis)

## Java
* See [Java ist auch eine Insel  (German)](http://openbook.rheinwerk-verlag.de/javainsel/)

## Travis-CI Yaml file
* See [Travis-CI docs](https://docs.travis-ci.com/)


### Example file for Java
```Yaml
language: java
matrix:
  include:
    - jdk: oraclejdk7
      env:
        - JDK_Test="Oracle JDK7 [ant]"
      script:
        - ant
    - jdk: oraclejdk8
      env:
        - JDK_Test="Oracle JDK8 [ant]"
      script:
        - ant
    - jdk: openjdk6
      env:
        - JDK_Test="open-JDK6 [ant]"
      script:
        - ant
    - jdk: openjdk7
      env:
        - JDK_Test="open-JDK7 [ant]"
      script:
        - ant
    - jdk: oraclejdk7
      env:
        - JDK_Test="Oracle JDK7 [maven]"
      script:
        - mvn test
    - jdk: oraclejdk8
      env:
        - JDK_Test="Oracle JDK8 [maven]"
      script:
        - mvn test
    - jdk: openjdk6
      env:
        - JDK_Test="open-JDK6 [maven]"
      script:
        - mvn test
    - jdk: openjdk7
      env:
        - JDK_Test="open-JDK7 [maven]"
      script:
        - mvn test
```

### Example file for C
```Yaml
# Travis CI configuration file

language: c

script:
  - gcc src/CCalc.c -o ./CCalc.o
  - gcc src/Test_CCalc.c -o ./Test_CCalc.o
  - ./CCalc.o

matrix:
  include:
    - os: linux
      dist: trusty
      sudo: false
      compiler: gcc
    - os: linux
      dist: trusty
      sudo: false   
      compiler: clang
    - os: osx
      osx_image: xcode7.2
      compiler: gcc
    - os: osx
      osx_image: xcode7.2
      compiler: clang

```

## Google C++ Testing Framework

[Intro to the Googletesting Framework](Googletest.md)

* See [Github Repository](https://github.com/google/googletest)
* [some Examples from Github](https://github.com/snikulov/google-test-examples)

### An Example:

```cpp
#include <algorithm>

#include "cpp_sorter.h"
#include "gtest/gtest.h"

TEST(cpp_sorter_test, char_arr_sort)
{
   char arr[] = {'a','b','c','d','e','f','g','h','a','b'};
   char eq[]  = {'a','a','b','b','c','d','e','f','g','h'};
   int sz = sizeof(arr)/sizeof(arr[0]);

   array_sort(arr, sz);

   for(int i=0; i<sz; i++)
 EXPECT_EQ(arr[i], eq[i]);
}

int main(int argc, char **argv) {
 ::testing::InitGoogleTest(&argc, argv);
 return RUN_ALL_TESTS();
}
```
## Junit5
* See [JUnit 5 User Guide](http://junit.org/junit5/docs/current/user-guide/)

## Spock
* See [Projects Homepage](http://spockframework.org/)
* [A tutorial](http://edgibbs.com/spock-intro-a-bdd-testing-framework-in-groovy/)

## GIT

### init your environment and create a local repo
```bash
git config core.autocrlf
git config --global user.name "<YOUR NAME>"
git config --global user.email "<YOUR MAIL ADDRESS>"
git init
git add <FILENAME|FOLDER>
git commit -a -m "<WHAT HAVE YOU DONE?>"
```

### Clone a remote repo and work on it
```bash
git clone <REPO>
git branch <WORKING BRANCH>
git checkout <WORKING BRANCH>
git add <FILENAME|FOLDER>
git commit -a -m "<WHAT HAVE YOU DONE?>"
git checkout master
git pull origin master --rebase
git checkout <WORKING BRANCH>
git rebase master
git checkout master
git merge <WORKING BRANCH> --ff-only
git push -u origin master
```

### Git Basic Courses
* [interactive course](http://learngitbranching.js.org/)
* [Pro Git](https://git-scm.com/book/en/v1)
* [Github](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)
* [Atlasian](https://www.atlassian.com/dms/wac/images/landing/git/atlassian_git_cheatsheet.pdf)

## The initial Repo and its rules
* See [README](../README.md)

# The Dojo
## Rules
* The development during the Dojo is done using Test-Driven-Development (TDD) or Behaviour-Driven-Development (BDD)
* During each DoJo session exactly one Kata (excercise) is done.
* The DoJo is divided into rounds of 5 minutes each with a 30 seconds break in between.
*	After 4 rounds a 10 minutes retrospective is done.
  * What was good bad during last rounds ?
  * What have we learned ?
  * What do we need for the next rounds ?
  * Common Questions on the Kata or the programming.
*	Katas are solved pairwise with a driver and a copilot. The driver is coding the tests and the solution. The copilot is supporting during code writing.
*	After each round driver and copilot are mixed up between groups.
*	Before the DoJo starts the decision to do the Kata in TDD or BDD has to be made. From this moment on the rules of this type of development have to be followed.
*	The documentation of all code and the Kata is done in a git repository.
* Each line of program code which is not intended to fulfill the success of a test case has to be delete by the copilot.
* After each round a git commit should be created.
* At least at the end of each Kata a push into the remote repository has to be done.

## Preparation
* Each participant will need at least a Github and a Travis-CI account connected to each other
  * You can create a Github accounte [here](https://github.com/)
  * You can create a Travis-CI account  [here](https://travis-ci.org/)
* Before the DoJo each participant should have an IDE installed and should have forked the initial repo with all necessary libraries.
  * Atom is a good choice for the IDE, but the Github-Editor is also sufficient
  * You will find the initial repo [here](https://github.com/TLoebner/codingdojo.git)

## Some sources of Katas
* [http://ccd-school.de/ (German)](http://ccd-school.de/coding-dojo/)

## During the DoJo
* At first create an empty class for the first part of the Kata
* Create test cases for the Kata
* Run the test cases
* Fill your class to implement the functions described by your test cases
* Create commits on a regularly base. If you are only testing using Travis-CI, create a commit after writing the test and after each step of implementation.
* At the end of the Kata all test cases have to run successful and a clean branch ready for merge with the initial repository have to be created
