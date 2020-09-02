# Embedded System Design Module

The following modules are designed for newcomers to the specific topic. If you feel like you are capable of all the modules (like if you have taken the ECE 362 course), please reach to the team lead of the embedded system team lead for advanced projects to work on.

In addition, we are not trying to include all the necessary details and information to get you started on basic skills like C and STM32. Instead, we will rely heavily on external, quality, online resources to get you started. The emphasis of the club is to get you start on the **Projects** instead teaching you hands by hands. You are **expected** to learn the necessary skills by yourself since this will be curical in your future academic life and career.

However, this does not mean that we prohibit you to ask for help! You can always reach out to us for help in the slack channel. Just keep it mind though, prior to ask question, do the following checklist to see if you already have the answer:

1. [ ] Have you use search engine to search your problem?
2. [ ] Have you use stackoverflow to search your problem?
3. [ ] Have you check the piazza and see if there is already an answer to your problem?
4. [ ] If you are using a library or set of APIs, have you read the documentation yet?

## Table of Contents

- [Embedded System Design Module](#embedded-system-design-module)
  - [Table of Contents](#table-of-contents)
  - [Tools Needed](#tools-needed)
  - [Programming Langague Prep (C learning module)](#programming-langague-prep-c-learning-module)
    - [Configure your environment](#configure-your-environment)
    - [Beginner in C](#beginner-in-c)
    - [Feeling good about C programming](#feeling-good-about-c-programming)
  - [Programming Platform Intro (STM32 Platform)](#programming-platform-intro-stm32-platform)
    - [Preparation](#preparation)
    - [How to learn](#how-to-learn)
    - [Projects](#projects)
    - [What goes beyond?](#what-goes-beyond)

## Tools Needed

Beside C and STM32 in the following sections, there are some other useful tools you should be familiar with to aid the collaboration and development.

1. [Markdown](https://guides.github.com/features/mastering-markdown/)
   1. A really, really simple styling format to present your documentation
   2. Like HTML, but way easier
   3. The above link points to the guide from GitHub and you should be able to master Markdown in less than 10 minutes
2. [Git](https://git-scm.com/)
   1. Git is a distributed version control software used extensively in software development
   2. We will use Git to manage both the embedded system code as well as the computer vision algorith,
   3. You can follow the installation guide in the Git official website if you haven't installed it yet (for Windows only probably)
   4. Also there is a quick guide the official website (or on search engine) as well. Make sure you understand as least the following commands:
        1. Help
            1. `git -h` and `git --help`
            1. `git COMMAND -h`
        1. Save progress
            1. `git add DIR` add the files or directory `DIR`
            2. `git commit -m "Commit message"` commit current progress with the message
        1. Branching
            1. `git branch NEW_BRANCH` creates a new branch with named `NEW_BRANCH`
            2. `git checkout BRANCH` switches to an existed branch named `BRANCH`
            3. `git checkout -b NEW_BRANCH` creates and switches to the new branch named `NEW_BRANCH`
            4. `git merge BRANCH` merges the current branch with the other branch named `BRANCH`
        1. Remote Repo interaction
            1. `git remote add REPO_NAME REPO_URL` adds the repository at `REPO_URL` with name `REPO_NAME`
            2. `git push REPO_NAME` pushes the locally committed code to the remote repository with name `REPO_NAME`
            3. `git pull REPO_NAME` fetches the remote repository and merges it with the current branch

3. [GitHub](https://github.com/)
   1. GitHub is a remote git repo hosting service website. We will be using it to host our code and collabrate with each other.
   2. You can register an account there and send the account to your team lead so that we can add you to our organization

## Programming Langague Prep (C learning module)

Since we will be merging the electrical team and control team together starting this semester, C language now becomes a necessary skill for member to possess.

### Configure your environment

Before you start the C learning module, please make sure that you have the environment needed for compiling C. The `C-ADT` project in the next section requires `make` and `gcc` to function properly. 

You can set up your environment in different OS by following this link [here](https://www.tutorialspoint.com/cprogramming/c_environment_setup.htm).

Another recommendation is that you can use [Visual Studio Code](https://code.visualstudio.com/) to edit your program file. Although the IDE we will be using later when programming the STM32 platform is adapted from Eclipse, having a simple and lightweight yet powerful text editor like vscode could help you substantially.

### Beginner in C

If you haven't met C before, here are two resources you can use to get familiar with.

1. [Introduction to C by Alex Allain](https://www.cprogramming.com/tutorial/c/lesson1.html)
2. [HackeRank C Learning](https://www.hackerrank.com/domains/c)
   1. You are expected to be able to complete the easy as well as medium problem listed here.
   2. You can try the hard problems if you like to do so, good practice is always encouraged.

### Feeling good about C programming

If you felt like you are comfortable with programming in C, please complete the basic data structure listed in this [repo](https://github.com/William-An/C-ADT).

To you clone this repository, navigate to the `Basic` folder, and change branch to `train`, use the following command:

    git clone https://github.com/William-An/C-ADT.git
    cd C-ADT
    git checkout train
    cd Basic

You should then start to read the `README.md` and become to code the basic data structure in C. You will need to use the `make` command to compile and link your code. Checkout the `makefile` for how to compile code and run test cases.

## Programming Platform Intro (STM32 Platform)

If you have used Arduino or similar embedded system before, then STM32 might be familiar to you. STM32 is an industrial level embedded system platform based on the ARM architecture (same as the CPUs in your phone, tablets, or even laptop (all hail mac)). However, unlike those fancy CPUs in smartphones, the STM32 is designed to be power efficient, low cost, and bunch of peripherals to interact with other sensors or chips. The control board used on our robot for chasis and glimbal control is based on the STM32F4 series chip which is more powerful then the STM32F0 series used in ECE 362.

### Preparation

To learn STM32, you will need a STM32 development board, obviously. You can choose the [STM32F0Discovery board](https://www.mouser.com/ProductDetail/STMicroelectronics/STM32F0DISCOVERY?qs=y%252BFWVGuMvwZK8miFvhZefg%3D%3D&gclid=Cj0KCQjwhb36BRCfARIsAKcXh6FOEcXheD8fQyVoYDymIGN6Ix_KNHVSjdSkVLNqkEVx7jcDj7Yq7eAaAn5fEALw_wcB) or the [NUCLEO-L476RG](https://www.mouser.com/new/stmicroelectronics/stm-nucleo-l476rg-development-board/?gclid=Cj0KCQjwhb36BRCfARIsAKcXh6FRLF2fN3jOrLzN6wMS1m-2AxDgY_0Kuyq0sUeyokR7DkOuu1LsWuQaAqkREALw_wcB) board. Both are developed by STMicroelectronics to aid the learning of its platform. As for recommendation, if you want to take the ECE 362 course, it might be good for you to choose the STM32F0Discovery since its chip (STM32F051R8T6) IS the only chip you are allowed to use in this course.

Besides the development board, you will also need the IDE (AC6’s System Workbench (in ECE 362) or STM32CubeIDE), which will be introduced in the next section.

In addition, you can purchase some sensor kits to try to read or write it on STM32 platform as well. If you have a arduino sensor kit, you can directly hook it up to your board and get start on it immediately!

### How to learn

So there are two ways (or 10 ways) to study STM32:

1. You can go with the blue pill, which is directly programming in HAL (hardware abstraction layer) library provided by STM32. It is also the library used by DJI in their official control code and thus our main controller board
   1. [Offical tutorial by STM32](https://www.st.com/content/st_com/en/support/learning/stm32-education/stm32-step-by-step.html)
   2. After completing the tutorial (step 1 - step 2 only), it is highly recommended you try out the onboard subsystem as well like
      1. UART
      2. I2C
      3. SPI
      4. GPIO
      5. Timer
      6. ADC/DAC
      7. DMA (direct memory access)
      8. Sensor interaction
      9. There should be plenty of resource out on the internet to aid you learning all these peripherals.
2. Or you can go with the red pill and dig deeper into STM32 by reading the family reference manual of your chip on board, the user's guide for your development board, and do the programming using the Stdperiph library as well as HAL library.
   1. Reading the manuals from STMicroelectronics allows you to have a clear understanding of the embedded system hardware. It is recommended you go with this way if you plan to take or have already taken ECE 362,  ECE 337 and ECE 437
   2. In addition, there are also official code example in the appendices of the manuals to help you understand as well
   3. You should also be able to understand and program the following peripherals/subsystems:
      1. UART
      2. I2C
      3. SPI
      4. GPIO
      5. Timer
      6. ADC/DAC
      7. DMA (direct memory access)
      8. Sensor interaction
3. Some reference materials that might be helpful
   1. Manuals of STM32 board and chips
   2. Datasheets of the sensor chips you plan to use

### Projects

Here are some possible STM32-based projects you can try out with your fellow members (in groups of 3 or 4)

1. Create a self-balanced two wheel robot that can be remotely controlled. Example video [here](https://www.youtube.com/watch?v=I6z26LVu5y0&t=65s)
   1. The video shown above use Arduino as controller board, you will need to use the STM32 platform (regardless of which development board you use) to achieve the same objective
   2. You can also refer to my project on this [here](https://github.com/William-An/Adjustic) to gain some insight on how to start
2. Create a 2-axis glimbal system that can stablize itself automatically, like the DJI's hand-held glimbal system.
3. Other projects you would like to try out!

### What goes beyond?

Hopefully by this point you have a clear understanding about the STM32 platform and how to program it. You will then need to read the exisiting code we have for our robots. Ask your team lead for further information