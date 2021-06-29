# :zap: Java Concurrency Threads
 
* Java coding project for a Java Programming Masterclass Section 15 Concurrency in Java- see [:clap: Inspiration](#clap-inspiration) below
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/java-concurrency-threads?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/java-concurrency-threads?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/java-concurrency-threads?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/java-concurrency-threads?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Angular Material Table](#zap-angular-material-table)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* [class Interface Lock](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/locks/Lock.html) used for controlling access to a shared resource by multiple threads.
* [class ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html) Resizable-array implementation of the List interface.
* [class concurrent locks - ReentrantLock](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/locks/ReentrantLock.html) reentrant mutual exclusion Lock with the same basic behavior and semantics as the implicit monitor lock accessed using synchronized methods and statements, but with extended capabilities

## :camera: Screenshots

![Example screenshot](./img/java.jpg)

## :signal_strength: Technologies

* [Java v11](https://www.java.com/en/)

## :floppy_disk: Setup

* Open folder in an IDE such as IntelliJ.

## :computer: Code Examples

* `Main.java` while loop that runs while buffer is unlocked

```java
while(true) {
    if(bufferLock.tryLock()) {
        try {
            if(buffer.isEmpty()) {
                continue;
            }
            System.out.println(color + "The counter = "+ counter);
            counter = 0;

            if(buffer.get(0).equals(EOF)) {
                System.out.println(color + "Exiting");
                break;
            } else {
            System.out.println(color + "Removed " + buffer.remove(0));
            }
        } finally {
            bufferLock.unlock();
        }
    } else {
        counter++;
    }
}
```

## :cool: Features

* N/A

## :clipboard: Status & To-Do List

* Status: Working.
* To-Do: Nothing

## :clap: Inspiration

* [Udemy: Java Programming Masterclass for Software Developers](https://www.udemy.com/course/java-the-complete-java-developer-course/learn/lecture/3561816#overview)

## :envelope: Contact

* Repo created by [ABateman](https://www.andrewbateman.org), email: gomezbateman@yahoo.com
