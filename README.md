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

It is a game that is used to test the knowledge acquired through the application. It will have categories such as numbers, colors, months of the year, days of the week and body parts.<br />
There will be a database that allows the game to take the question and the answer and show it to the player. <br />

![Englisher](https://i.imgur.com/9EOJl2z.png)


For the game we created the layout of the homepage for that I inserted the logo an image as background and we created two buttons one to start the game and another that will contain the instructions for the player.


```ruby

   
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignBottom="@+id/button2"
        android:layout_centerHorizontal="true"
        android:layout_marginLeft="118dp"
        android:layout_marginTop="380dp"
        android:layout_marginBottom="68dp"
        android:background="@drawable/buttonshape"
        android:text="Começar"
        android:textAlignment="center" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="109dp"
        android:layout_marginTop="450dp"
        android:layout_marginBottom="0dp"
        android:background="@drawable/buttonshape"
        android:text="Instruções"
        android:layout_centerHorizontal="true"
        android:textAlignment="center" />

    <ImageView
        android:id="@+id/imageView3"
        android:layout_width="250dp"
        android:layout_height="180dp"
        android:layout_centerHorizontal="true"
        android:layout_marginLeft="109dp"
        android:layout_marginTop="170dp"
        android:layout_marginBottom="0dp"
        app:srcCompat="@drawable/gamelogo" />

```

The first page I created was the instructions page and for that I used the function "onCreateDialog" that allows to create a pop-up window when clicking on the button.

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

It is a game that is used to test the knowledge acquired through the application. It will have categories such as numbers, colors, months of the year, days of the week and body parts.<br />
There will be a database that allows the game to take the question and the answer and show it to the player. <br />

![Englisher](https://i.imgur.com/9EOJl2z.png)


For the game we created the layout of the homepage for that I inserted the logo an image as background and we created two buttons one to start the game and another that will contain the instructions for the player.


```ruby

   
 public Dialog onCreateDialog(Bundle savedInstanceState) {
        AlertDialog.Builder builder=new AlertDialog.Builder(getActivity());
        builder.setTitle("Instruções")
                .setMessage("\n" +

```

Right after that I made a button to start the game and added a "Spinner" which allows the player to choose which level of difficulty they want to test.


![Englisher](https://i.imgur.com/G8d2WfD.png)




```ruby

   
 <Spinner
        android:id="@+id/spinnerDifficulty"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"

        android:layout_below="@+id/button3"
        android:layout_alignStart="@+id/button3"
        android:layout_marginTop="40dp" />

```
I created a third activity to start the quiz.

```ruby

   
  Button buttonStartQuiz = findViewById(R.id.button3);
        buttonStartQuiz.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                startQuiz();
            }
        });
```
I moved on to the Quiz layout.<br />
First I used "TextView" to show the player the points, the number of questions and the difficulty they are playing.

```ruby

 <TextView
       android:id="@+id/text_pont"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:text="Pontos: 0"
       android:textColor="@android:color/black"
       android:freezesText="true"
       />

    <TextView
        android:id="@+id/text_conta"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Pergunta: 1/5"
        android:textColor="@android:color/black"
        android:layout_below="@+id/text_pont"
        android:freezesText="true"/>

```




![Englisher](https://i.imgur.com/LpsE4Cz.png)  




I added another "TextView" for the timer.

![Englisher](https://i.imgur.com/A50kgJg.png) 


I added a "RadioGroup" to answer the questions. <br />And the respective "RadioButtons".


```ruby

 <RadioGroup
        android:id="@+id/radio"
        android:layout_centerVertical="true"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">

        <RadioButton
            android:id="@+id/radio_1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Opção 1"
            android:freezesText="true"/>

        <RadioButton
            android:id="@+id/radio_2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Opção 2"
            android:freezesText="true"/>

        <RadioButton
            android:id="@+id/radio_3"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Opção 3"
            android:freezesText="true"/>>

```

Under the "RadioGroup" I entered the button that will confirm the player's answer.

![Englisher](https://i.imgur.com/kZHXqoh.png) 

```ruby

  <Button
        android:id="@+id/button_confirm"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Confirmar"
        android:layout_below="@+id/radio"
        android:layout_marginTop="16dp"
        android:freezesText="true"/>

```
After having the game layout done I created a class, which stores the information about the questions, the answers, the difficulty and the correct answer, which will then be added to the internal database.

![Englisher](https://i.imgur.com/2zpPbcw.png) 


```ruby

 
public class Pergunta implements Parcelable {
    public static final String DIFFICULTY_EASY = "Facil";
    public static final String DIFFICULTY_MEDIUM = "Medio";
    public static final String DIFFICULTY_HARD = "Dificil";

    private String question;
    private String option1;
    private String option2;
    private String option3;
    private int answerNr;
    private String difficulty;

```
I've introduced a new class that will store constants for later use in SQL commands.<br />
I inserted the table that will have the questions in the database.<br />


![Englisher](https://i.imgur.com/pGJGraO.png) 

```ruby

 
public static class QuestionsTable implements BaseColumns {
    public static final String TABLE_NAME = "quiz_questions";
    public static final String COLUMN_QUESTION = "question";
    public static final String COLUMN_OPTION1 = "option1";
    public static final String COLUMN_OPTION2 = "option2";
    public static final String COLUMN_OPTION3 = "option3";
    public static final String COLUMN_ANSWER_NR = "answer_nr";
    public static final String COLUMN_DIFFICULTY = "difficulty";

}
}
```

From here I had to enter another class that with the help of the constants will create an internal database to save the questions and answers.


![Englisher](https://i.imgur.com/XmkTymU.png) ![Englisher](https://i.imgur.com/G3g2B35.png) 


I used two new constants for the name of the database and the version because whenever any question is changed the version will also have to be different.


```ruby

 
public class QuizDbHelper extends SQLiteOpenHelper {
    private static final String DATABASE_NAME = "englishergame.db";
    private static final int DATABASE_VERSION = 21;
```

I created a variable for the database.



```ruby

 
 private SQLiteDatabase db;
```


I created the table of questions in the database.

```ruby

 public void onCreate(SQLiteDatabase db) {
        this.db = db;
        final String SQL_CREATE_QUESTIONS_TABLE = "CREATE TABLE " +
                QuestionsTable.TABLE_NAME + " ( " +
                QuestionsTable._ID + " INTEGER PRIMARY KEY AUTOINCREMENT, " +
                QuestionsTable.COLUMN_QUESTION + " TEXT, " +
                QuestionsTable.COLUMN_OPTION1 + " TEXT, " +
                QuestionsTable.COLUMN_OPTION2 + " TEXT, " +
                QuestionsTable.COLUMN_OPTION3 + " TEXT, " +
                QuestionsTable.COLUMN_ANSWER_NR + " INTEGER, " +
                QuestionsTable.COLUMN_DIFFICULTY + " TEXT" +
                ")";
```


Besides the "onCreate" function there is also the "onUpgrade" function for when we need to update the database.<br />
Now we use another method in this case "fillQuestionsTable" so we can fill the database table with the data.<br />


```ruby

  private void fillQuestionsTable() {
        Pergunta pergunta = new Pergunta("Fácil: Como se escreve verde em Inglês ?",
                "Green", "Grin", "Gren", 1, DIFFICULTY_EASY);
        addQuestion(pergunta);
        Pergunta pergunta2 = new Pergunta("Fácil: Qual o número correspondente ao número 16",
                "Seventeen", "Sixteen", "Fifteen", 2, DIFFICULTY_EASY);
        addQuestion(pergunta2);
        Pergunta pergunta3 = new Pergunta("Fácil: O meu aniversário é em Outubro",
                "November", "July", "October", 3,  DIFFICULTY_EASY);
        addQuestion(pergunta3);
        Pergunta pergunta4 = new  Pergunta("Fácil: Que dia vem a seguir a segunda-feira?",
                "Tuesday", "Thursday", "Sunday", 1,  DIFFICULTY_EASY);
        addQuestion(pergunta4);
        Pergunta pergunta5 = new Pergunta("Fácil: Como se escreve mão em Inglês?",
                "Hand", "Head", "Mouth", 1, DIFFICULTY_EASY);
        addQuestion(pergunta5);
```


We entered the questions, the answers and the difficulty in the database.




```ruby

  private void addQuestion(Pergunta question) {
        ContentValues cv = new ContentValues();
        cv.put(QuestionsTable.COLUMN_QUESTION, question.getQuestion());
        cv.put(QuestionsTable.COLUMN_OPTION1, question.getOption1());
        cv.put(QuestionsTable.COLUMN_OPTION2, question.getOption2());
        cv.put(QuestionsTable.COLUMN_OPTION3, question.getOption3());
        cv.put(QuestionsTable.COLUMN_ANSWER_NR, question.getAnswerNr());
        cv.put(QuestionsTable.COLUMN_DIFFICULTY, question.getDifficulty());
        db.insert(QuestionsTable.TABLE_NAME, null, cv);
```
Now I had to find a way to get the questions out of the database to show them.<br />
So I created an "ArrayList" and passed the name of the table as values.<br />


```ruby

  ArrayList<Pergunta> questionList = new ArrayList<>();
        db = getReadableDatabase();
        Cursor c = db.rawQuery("SELECT * FROM " + QuestionsTable.TABLE_NAME, null);

```

I created a variable so that the player can then know from the colour of the answer whether it is right or wrong.


```ruby

  private ColorStateList textColorDefaultCd;

```

I used more variables to count the number of questions, another one that saves the total number of questions and another one that saves the question number the player is in.


```ruby

 private int questionCounter;
    private int questionCountTotal;
    private Pergunta currentQuestion;

```

And a variable that will save the number of points the player has achieved.



```ruby

     private int score;

```

Every time you change the question the radio buttons return to the initial color and none of the answers are selected.


```ruby

      private void showNextQuestion() {
        rb1.setTextColor(textColorDefaultRb);
        rb2.setTextColor(textColorDefaultRb);
        rb3.setTextColor(textColorDefaultRb);
        rbGroup.clearCheck();

```

If there are still questions, the game will show the next question if there is no Quiz ends and returns to the home page.


```ruby

      if (questionCounter < questionCountTotal) {
            currentQuestion = questionList.get(questionCounter);

            textViewQuestion.setText(currentQuestion.getQuestion());
            rb1.setText(currentQuestion.getOption1());
            rb2.setText(currentQuestion.getOption2());
            rb3.setText(currentQuestion.getOption3());

            questionCounter++;
            textViewQuestionCount.setText("Pergunta: " + questionCounter + "/" + questionCountTotal);
            answered = false;
            buttonConfirmNext.setText("Confirmar");

            timeLeftInMillis = COUNTDOWN_IN_MILLIS;
            startCountDown();
        } else {
            finishQuiz();
        }
```


Now we have to see if any Radio buttons have been selected.

```ruby

    @Override
            public void onClick(View v) {
                if (!answered) {
                    if (rb1.isChecked() || rb2.isChecked() || rb3.isChecked()) {
                        checkAnswer();
                    } else {
                        Toast.makeText(num.this, "Seleciona uma resposta", Toast.LENGTH_SHORT).show();
                    }
                } else {
                    showNextQuestion();
                }
            }
```
If no answer is selected, a "Toast" appears, a small text box saying "Select an answer".<br /><br />

You must validate whether the answer is correct or wrong, so if the answer is correct it will increase one point and regardless of whether the answer is right or wrong it will show the correct answer.


```ruby

  private void checkAnswer() {
        answered = true;

        countDownTimer.cancel();

        RadioButton rbSelected = findViewById(rbGroup.getCheckedRadioButtonId());
        int answerNr = rbGroup.indexOfChild(rbSelected) + 1;

        if (answerNr == currentQuestion.getAnswerNr()) {
            score++;
            textViewScore.setText("Pontos: " + score);
        }

        showSolution();
    }
```


To validate the color of the answer a case is used so that if the answer is right the color of the option will turn green.

```ruby

  private void showSolution() {
        rb1.setTextColor(Color.RED);
        rb2.setTextColor(Color.RED);
        rb3.setTextColor(Color.RED);

        switch (currentQuestion.getAnswerNr()) {
            case 1:
                rb1.setTextColor(Color.GREEN);
                textViewQuestion.setText("Resposta 1 esta correta");
                break;
            case 2:
                rb2.setTextColor(Color.GREEN);
                textViewQuestion.setText("Resposta 2 esta correta");
                break;
            case 3:
                rb3.setTextColor(Color.GREEN);
                textViewQuestion.setText("Resposta 3 esta correta");
                break;
        }
        
```
If it is not the last question after the player has answered and confirmed the answer the button will say next and when clicking passes the next question if it is the last one it says exit and return to the initial page.

```ruby

 if (questionCounter < questionCountTotal) {
            buttonConfirmNext.setText("Proximo");
        } else {
            buttonConfirmNext.setText("Sair");
        }
        
```

To change the color of the timer when it reaches 10 seconds I used the same type of code as the radio buttons.<br />
To format how the time appears I used the function "timeFormatted".<br />
And so the function is ready to be used.

```ruby

 private void updateCountDownText() {
        int minutes = (int) (timeLeftInMillis / 1000) / 60;
        int seconds = (int) (timeLeftInMillis / 1000) % 60;

        String timeFormatted = String.format(Locale.getDefault(), "%02d:%02d", minutes, seconds);

        textViewCountDown.setText(timeFormatted);

        if (timeLeftInMillis < 10000) {
            textViewCountDown.setTextColor(Color.RED);
        } else {
            textViewCountDown.setTextColor(textColorDefaultCd);
        }
    }
        
```

Then I used the previous function for when the timer reaches zero, in the next question back to 30 seconds.

```ruby

  @Override
            public void onFinish() {
                timeLeftInMillis = 0;
                updateCountDownText();
                checkAnswer();
            }
        }.start();
```

In the end the layout of the Quiz will look like this.


![Englisher](https://i.imgur.com/YKwssW1.png)



This is the final result of the database I created.



![Englisher](https://i.imgur.com/HVVYtua.png)


To open the database on the computer I also used the program "DB Browser (SQLite)".<br />You can install it through this link:
https://sqlitebrowser.org/dl/


## Conclusion


+ You learned how to use Android Studio. 
+ The various functions.
+ More about how to use the Java language.
+ How to make a database in SQLite.

