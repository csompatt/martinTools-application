# martintools-app

https://csompatt.github.io/martinTools-application/

## Description

```
Changing tools in a CNC machine is a part of my everyday work, and this application helps me to do it faster and easier.
Before I invented this application, I used to do everything manually which took me at least a half-hour daily, now it's no more than 2 minutes.
```

### Technologies
```
- HTML5
- CSS
- JavaScript
- Vue.JS CLI
```

# How it works?
```
We suppose that our CNC machine can mill 3 different items.
Every item has a different program and every program needs to work with 5 different tools.

```

<img width="583" alt="Képernyőfotó 2022-07-11 - 21 26 56" src="https://user-images.githubusercontent.com/61659027/178342869-fbb52c89-1f34-4a62-a1d6-7693baba1040.png">



### Items tools list:
```
Item 1:       Item 2:       Item 3:

Nr. 1         Nr. 5         Nr. 4
Nr. 2         Nr. 6         Nr. 5
Nr. 3         Nr. 7         Nr. 8
Nr. 4         Nr. 8         Nr. 9
Nr. 5         Nr. 9         Nr. 10
                            Nr. 11
                            Nr. 12
```
```
When I’m finished with every piece of an item, 
I take out the tools that I don’t need anymore and put new ones into the machine for the next item.

The new item is Item 4:

Nr. 1      
Nr. 13
Nr. 14
Nr. 15
```
### After finished items:

```
We suppose that I finished every piece from item 1 and I have to take out the tools, which I don't need for the other items.

Before my application, I had to open every program and search every tool in order to know which one is necessary.
With my application we have only one task to do, add the item numbers, click on the button and we have the result of which tools could we take out.
```

<img width="516" alt="Képernyőfotó 2022-07-11 - 21 26 30" src="https://user-images.githubusercontent.com/61659027/178342832-6c09fa02-ee8b-4ddc-8b1c-1023252e6807.png">


In our example, we can take out the tool Nr. 2 and Nr. 3.
