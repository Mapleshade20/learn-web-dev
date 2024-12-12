# Introduction to Web Development

## Pitfalls to Avoid

#### [A note on AI code generation](https://www.theodinproject.com/lessons/foundations-motivation-and-mindset#a-note-on-ai-code-generation)

We do not recommend using AI tools for your learning.

#### Procrastination

Procrastination will be your biggest enemy when trying to make progress.

**Solution:** The [Pomodoro Technique](https://pomofocus.io) is a way of managing your time in order to stay focused. 
The idea is to set a timer for 25 minutes and to work on a task until the timer goes off.
If you get distracted or interrupted during the 25 minutes, start the 25 minutes of work over again.
Once you’ve successfully focused on work for 25 minutes, take a 5 minute break.
After you’ve completed four 25 minute blocks of work, take a longer 15-30 minute break.

#### Not taking breaks

**Solution:** Use the previously mentioned **Pomodoro Technique** to time how often and how long to take your well-deserved breaks. Feel free to play around and experiment with different frequencies and durations of breaks.

#### Digital distractions

**Solution:** Turn off notifications and add a blocker to your Internet to limit your time on distracting sites.

#### Physical distractions

**Solution:** Find a quiet place; use noise canceling headphones. There are also libraries that are serene and comfortable. Beyond just providing a pleasant study space, the presence of others studying around you instills a sense of productivity.

#### Rabbit holes

So many high quality courses and tools $\to$ easy to get pulled into rabbit holes by spending time trying to learn all there is to know about a subject that they aren’t ready for or won’t benefit them much.

**Solution:** Stick to the path laid out as much as possible. Try to limit time spent going down rabbit holes, as these sidetracks can really ruin your momentum.

#### Comparing yourself to others

Students often compare themselves to others who are farther along in their coding journey or have more experience. This is a recipe for depression and frustration.

**Solution:** Only compare yourself to your past self. Have your abilities and knowledge improved from where you were last week, last month, or last year? Be proud of the progress that you’ve made!

#### Counterproductive note-taking

The Odin Project does not recommend taking a lot of notes throughout your web development educational journey because it can be time-consuming and often leads to wasted effort.

**Solution:** Instead of taking notes to use as direct references, make notes that can serve as prompts for further research. It is important to get comfortable with reading documentation, which essentially acts as pre-existing notes made by someone else.



## Asking For Help

#### Always provide your code and the surrounding context

When asking a question, it is essential to provide your **code, error message, terminal command, server output, and other relevant details**. You should provide as much context as possible and zero in on the specific problem, such as pointing people to a specific function or line number in your code. Providing this relevant information makes it easier for others to help you.

If your question does not provide any code or other relevant information, it will be difficult for others to help you. In order to fully understand your question, there will be a lot of unnecessary back and forth conversation. This can be discouraging for you because any answers with incomplete information will not solve your problem. This process can be frustrating for those helping because the meaning of your original question changes as you add more context to it. 

If you truly want to ask a conceptual question, you should indicate this as part of your question.

#### Ask about the problem at hand, not the solution itself

A lot of learners ask exactly how to approach a given task or assignment in this curriculum, such as the following:

>  “How do I complete Step 5 of the Rock Paper Scissors Assignment”?

Keep in mind that you’re supposed to figure out how to solve the assignments yourself, and figuring out an approach is essential to your learning journey. A much better question might look like this:

>  “Hey, I’m trying to return a string that displays the winner in Rock Paper Scissors, but I’m getting a syntax error on line 12. How can I fix this? Here’s my code.”

In sharing your attempt, people know what you’ve tried and won’t suggest things that might not have worked out for you. It also allows them to debug your current iteration of code, rather than sending you down a path that has you start all over again when you might be very close to a solution.

Now, if you’re completely stuck with where to start, it’s completely fine to let people know that you’re stuck. Asking where you can start and what you can research to get on the right track empowers you to be able to resolve issues largely on your own in the future, and might even empower you to help others with the same issue later on. It is also recommended that you share your pseudo code so people can nudge you in the right direction or correct any misunderstandings you may have.

#### Don’t take asking for more context to heart

People who volunteer in coding communities are here to help! A question you may feel is coherent and “obvious” probably isn’t if you are being asked for more context. While something may seem “obvious” to a beginner, it’s sometimes nowhere near “obvious” to an expert. An expert knows about many, many more situations that could cause an issue someone is experiencing, and would want to refrain from sending a learner down the wrong path. People take time out of their day to help, so make it as easy as possible for them to help you! There’s probably a good reason why they need more information, so trust their judgment and experience when they ask. Many people who help in coding chats are unpaid volunteers, and are in no way obligated to answer your query. But because they truly want to help you, they will ask for more information when needed!



## Meet HTML, CSS, JavaScript

Normally HTML(Hyper Text Markup Language) and CSS(Cascading Style Sheets) doesn't do any logic. They just present elements in a static way. In contrast, JavaScript is a language that instructs things to function.

#### HTML example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <link rel="stylesheet" href="./styles.css">
  <title>Document</title>
</head>
<body>
  <h1>This is a first level heading in HTML. With CSS, I will turn this into red color</h1>
  <h2>This is a second level heading in HTML. With CSS, I will turn this into blue color</h2>
  <h3>This is a third level heading in HTML. With CSS, I will turn this into green color</h3>
  <p>This is a <em>paragragh</em> As you can see, I placed an empahisis on the word "paragraph". Now, I will change also
    the background color of the word "paragraph" to black, and its text color  to green, all with just CSS.</p>
  <p>The main essence of this tutorial is to:</p>
    <ul>
       <li>Show you how to format a web document with HTML</li>
       <li>Show you how to design a web page with CSS</li>
       <li>Show you how to program a web document with JavaScript</li>
    </ul>

  <p>Next, I am going to add the following two numbers and display the result, all with JavaScript<p/>
    <p>First number:<span id= "firstNum">2</span> <br></p>
    <p>Second number: <span id= "secondNum">7</span> </p>
    <p>Therefore, the sum of the two of those numbers is: <span id= "answer">(placeholder for the answer)</span></p>
    <input type="button" id="sumButton" value="Click to add!">
</body>
</html>
```

#### CSS example

CSS accesses elements by selecting them, like `h1{...}`. You can select a single or multiple web elements and specify how you want them to look or be positioned.

```css
h1 {
  background-color: #ff0000;
}

h2 {
  background-color: #0000FF;
}

h3 {
  background-color: #00FF00;
}

em {
  background-color: #000000;
  color: #ffffff;
}
```

#### JavaScript example

```js
function displaySum() {
  let firstNum = Number(document.getElementById('firstNum').innerHTML);
  let secondNum = Number(document.getElementById('secondNum').innerHTML);

  let total = firstNum + secondNum;
  document.getElementById("answer").innerHTML = ` ${firstNum} + ${secondNum}, equals to ${total}` ;
}

document.getElementById('sumButton').addEventListener("click", displaySum);
```

