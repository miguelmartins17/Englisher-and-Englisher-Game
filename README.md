# Englisher-and-Englisher-Game
My presentation
==========

Hello I am Miguel, I just finished my course in computer systems management and programming with the best grade in my class.

For my final project, I created an application and a game, for all people looking to learn basic things in English.


![Englisher](https://i.imgur.com/sG4aLJL.png)      			 		      ![EnglisherGame](https://i.imgur.com/w5SXbC0.png)



Alone I studied and researched how to use Android studio to my advantage and came to share the knowledge I acquired. 

## Why?
Why learn English ?
Is it really worth learning this language?
These are some questions that regularly go through the heads of several people every day.

My goal with this application is to help you learn one of the most used languages in the world.

## What?

This tutorial will help you get started with
Android Studio.<br />
I'm here to share all the knowledge I've learned from the android studio and show you the whole process until the end of the application and the game.

### Pre-Requisites

+ **A computer** with a web browser
+ **Internet access** to download the Android Studio
+ **Time and Patience** 
+ **_Basic_ Programming Skills** (Java)

## How?

The first thing to do is  `install ` the android studio - https://developer.android.com/studio <br />
After having the installation done we will need to choose the initial activity of the application so that we can make all the changes to the layout.<br />
For this I used the empty activity provided by android studio.


![Englisher](https://i.imgur.com/I9rbg1K.png)  

Now with the activity blank we have  `created ` the page that will contain the introduction of the application in order to explain the objective of it.<br />

To enter text on the page we use the  `TextView ` function.

```ruby
   <TextView
        android:id="@+id/textview1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="80dp"
        android:text="Introdução"
        android:textSize="20sp"
        android:textStyle="bold" />

<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_below="@+id/textview1"
    android:textAlignment="center"
    android:text="@string/intro"
    android:layout_marginTop="180dp"
    android:padding="0dp"
    android:layout_centerHorizontal="true"
    android:layout_alignParentTop="true"
    android:layout_marginHorizontal="10dp"/>
```


Now after we enter the text the page will look like this.

  ![Englisher](https://i.imgur.com/04Awgns.png)  


## Menu

Let's move on to one of the most important parts which is the application ` menu `. <br />
The menu consists of two parts the options of the menu and the design of the same.


![Englisher](https://i.imgur.com/i9CcKDJ.png)      ![Englisher](https://i.imgur.com/CAgwLUx.png)   


To join the two parts of the menu we use another function called app.<br />


```ruby
   <android.support.design.widget.NavigationView
        android:layout_height="match_parent"
        android:layout_width="wrap_content"
        android:id="@+id/nav_view"
        app:menu="@menu/drawer_menu"
        app:headerLayout="@layout/nav_header"
        android:layout_gravity="start"/>
```




This function allows us to use two parts in this case the  `nav_view ` and the  `drawer_menu `.
And so we'll have our menu.

![Englisher](https://i.imgur.com/01E17El.png) 

Now we'll have to prepare all the  `menu ` options to be functional.<br />
For each menu option a fragment is created a function that makes the creation of pages easier.

![Englisher](https://i.imgur.com/sbkiLcE.png) 

## Menu options

We start by editing the first fragment by creating a table and placing a button that will be used to hear the words saved in the table.<br />

```ruby
    <TableLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginVertical="130dp"
            android:layout_marginHorizontal="10dp"
            android:background="#f1f1f1"
            android:padding="40dp">


            <TableRow
                android:gravity="center_horizontal|fill_vertical"
                android:orientation="vertical">

                <TextView

                    android:layout_width="wrap_content"
                    android:layout_height="match_parent"
                    android:layout_marginTop="0dp"
                    android:layout_marginRight="1dp"
                    android:layout_marginBottom="1dp"
                    android:layout_weight="1"
                    android:background="#ffffff"
                    android:gravity="center"
                    android:padding="5dp"
                    android:text="Oi"
                    android:textStyle="bold" />

                <TextView

                    android:layout_width="wrap_content"
                    android:layout_height="match_parent"
                    android:layout_marginTop="0dp"
                    android:layout_marginRight="1dp"
                    android:layout_marginBottom="1dp"
                    android:layout_weight="1"
                    android:background="#ffffff"
                    android:gravity="center"
                    android:padding="5dp"
                    android:text="Hi"
                    android:textStyle="bold" />

                <Button
                    android:id="@+id/button_sound1"
                    android:layout_width="100dp"
                    android:layout_height="50dp"
                    android:layout_marginTop="0dp"
                    android:layout_marginRight="1dp"
                    android:layout_marginBottom="1dp"
                    android:layout_weight="1"
                    android:background="#0bcce6"
                    android:drawableTop="@drawable/ic_ouvir"
                    android:gravity="center"
                    android:onClick="playSound"
                    android:padding="5dp"
                    android:textStyle="bold" />
            </TableRow>

```

All the fragments are edited in the same way because they will all contain a table and the respective buttons so that the user can hear the correct pronunciation of each word.<br />

For the sound buttons to work we use the `raw` and `mediaplayer` function of android studio.<br />
The `raw` function allows you to add sound files to the project, but not only, it also allows you to add text files.<br />

And the `mediaplayer` allows us to play the saved sound files.

![Englisher](https://i.imgur.com/ahROeHh.png)   ![Englisher](https://i.imgur.com/v54frGB.png) 


For when the user clicks on the buttons the sound is played we use the `onclicklistener` function.

```ruby
 s1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                sound.start();

            }
        });
        s2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                sound2.start();
            }
        });
```

This will be the final layout for the information pages.

![Englisher](https://i.imgur.com/Aa8aY0l.png)

The only page in the menu that is different and does not carry information through the table is the contacts page that simply appears the phone number and email .<br />
Through the asset vector we choose the icons that will appear to represent in this case the mobile phone number and email.And like the others to put any kind of text we use TextView again.

![Englisher](https://i.imgur.com/dVEzNfO.png)

```ruby

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@color/cardview_light_background"
            android:padding="25dp">

            <ImageView
                android:layout_width="36dp"
                android:layout_height="36dp"
                android:src="@drawable/ic_email" />

            <TextView
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_gravity="center_vertical"
                android:padding="20dp"
                android:text="miguelguilherme2001@gmail.com" />

        </LinearLayout>

```

## The Game / Quiz

This is the first page that appears to the user when starting the game.

![Englisher](https://i.imgur.com/9EOJl2z.png)


