---
title: "The Monty Hall Problem"
date: 2022-04-17T00:47:00-05:00
draft: false

tags: ["monty_hall_problem", "to script or to not script"]

featuredImagePreview: "images/post_images/monty_hall.jpg"
lightgallery: true

summary: Behind three doors (A, B, C), one of them has a car and the others are empty. You pick door A and I open door B to show that there is nothing behind the door. Now, I give you a choice of switching your door to door C or stay with door A. What would you do?

---

### Let's Make a Deal

The Monty Hall problem is based on the game show, "Let's Make a Deal", originally hosted by Monty Hall himself. The contestant on the show was presented with three doors and asked to pick one door. Let's say you pick Door 1. Then Monty Hall, the host, will open one of the others to show that it's not the car.

![Doors](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Monty_open_door.svg/1200px-Monty_open_door.svg.png)

You are then asked if you would like to switch doors. Would you believe me if I told you it is a better decision to switch doors? Mathematically, you have a $66.6666$% chance of getting the car by switching doors. 

### The Mathematics
First, let's take step back. In the beginning, you had a $1/3$ chance of selecting the car. And a $2/3$ chance of not selecting the car or a $2/3$ chance that the car is in the other doors. And when a non-car door is opened and you are asked if you would switch then it means that the other has a $2/3$ of having the car behind it. Thus, it is best to switch doors. I would recommend Numberphile's video on [Monty Hall Problem](https://www.youtube.com/watch?v=4Lb-6rxZxx0). 

### The Code
Being a software engineer, I wanted to test this theory using code. Essentially, I implemented the game show for any number of doors that user provides as long as there are at least 3 doors. And you pick the trials too.

Below is a table of percentages the car was in the first door picked vs the door you switch for:

|Trials   |First Choice Door|Switch Door|
|:-------:|:---------------:|:---------:|
|1        |      0.00%      |  100.00%  |
|10       |     40.00%      |   60.00%  |
|100      |     32.00%      |   68.00%  |
|1000     |     33.10%      |   66.90%  |
|10000    |     34.06%      |   65.94%  |
|1000000  |     33.30%      |   66.70%  |
|10000000 |     33.31%      |   66.69%  |
|100000000|     33.33%      |   66.67%  |

While with three doors, we can see that switch door had the car roughly around $2/3$ or $66.67$% of the time. The percentages become more apparent when you leverage more than 3 doors. Below is the results of when we have 100 doors and you are asked to switch after 98 doors have been opened for you. 

|Trials   |First Choice Door|Switch Door|
|:-------:|:---------------:|:---------:|
|1        |      0.00%      |  100.00%  |
|10       |      0.00%      |  100.00%  |
|100      |      1.00%      |   99.00%  |
|1000     |      0.70%      |   99.30%  |
|10000    |      1.18%      |   98.82%  |
|1000000  |      0.99%      |   99.01%  |

As the data shows, you have roughly $99/100$ or $99$% chance of picking the car by switching doors at the end. 

If you want to run the script yourself, you can find my script in the [to_script_or_to_not_script](https://github.com/ahmadnazeri/to_script_or_to_not_script) repository. 
