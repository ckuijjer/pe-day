# Hello World

pre-readings: [](https://codeburst.io/react-js-for-beginners-the-basics-87ef6e54dae7)

In this workshop you will learn some basic understanding of coding tasks and software engineering. No prerequisite knowledge is required as the material is designed to take you through the required steps. Follow along, and raise your hand if you need assistance or have questions. You will work in groups of two or three people. 

After taking this workshop you have learned:

- How to *write some code*
- What *pair programming* is and how it can help
- What the programming languages *JavaScript* and *CSS* do and are used for
- What a *function* is in a programming language
- To work in a *development environment* as normally used by software engineers
- How open source communities use techniques like *forks* and *pull requests* to contribute to each others projects
- How we use the AWS cloud to build the API that powers this app

>A **Hello World** program is a computer program that outputs or displays the message "Hello, World!". Traditionally it is the first program software engineers write when learning to code, or when learning a new technology. In this workshop we will go beyond the simple Hello World program and have prepared a fully functional app for you to make small changes.

> You will work together in a small group. Working in pairs is common technique used by software engineers and is called **pair programming**. In this technique one of the engineers is called the *driver* and the other the *navigator*. The driver is in control and working the keyboard, whereas the thinker is reviewing the code written as well as sharing thoughts and keeping the bigger picture in mind. This technique can help increase quality, reduce defects and share knowledge.

Let's get started.

## Visit the CodeSandbox
The CodeSandbox is an online environment which resembles the coding environment software engineers use on a daily basis. On of the most popular code editors of today is VSCode. The CodeSandBox can be thought of as an online version of VSCode.

Follow this link https://codesandbox.io/s/plant-a-tree-pe-day-jh36j.

Take some time to get familiar with the CodeSandbox application.

![CodeSandbox.png](/images/image1.png)

The three main elements of the application:

1) File Explorer
Use this to switch between files
2) Code Editor
This is where you will make changes to code
3) Running App
This is the running app. Every time you make changes to the code the running app will update accordingly.

## Fork the code

Press the "Fork" button that is located in the upper right part of the screen. This will give you your own copy of the application your can work on.

> Creating a **fork** is one of the main mechanisms the open source community uses to make contributions to a code base that is owned by someone else. You can find the source code of most open source projects on **GitHub**, which is the worlds most popular site when it comes to sharing code.
>
>On GitHub When you want to make changes to a project, you fork it and make the changes in your own copy of the code. When you are ready you can request the original owners to merge you code changes to the main project. You do this by creating a **pull request**. After the owners review your code they can approve and merge the pull request after which your code is added to the main project.

## Assignment 1) Implement your first user story, make the plus button work.

You will now write some code to fulfil a user requirement. To make things easy we will provide you with a code snippet you can copy and paste into your editor.

The user story you will implement is as follows:

---
*User story*: As a user I want the plus button to increase the number of trees and I want the amount to be recalculated accordingly so that I have all the information I need to proceed to the next step for planting trees.

---

Go ahead and click green plus button in your app. You will notice that nothing happens. It is up to you to write the code to implement this functionality.

Inspect the code in the code editor. Make sure the file App.js is opened. Looking at the code you will find the following line:

```javascript
const increaseNumberOfTrees = () => {};
```

Replace this line with the following code snippet
```javascript
  const increaseNumberOfTrees = () => {
    const newNumberOfTrees = numberOfTrees + 1;
    setNumberOfTrees(newNumberOfTrees);
  };
```

There you go. Press the plus button again and you will see that everything works as expected.

> increaseNumberOfTrees as seen above is called a **function**. A function implements some logic and can be called from other locations in the code. As an example of calling a function see the line with setNumberOfTrees. This function is defined somewhere else and used from within the increaseNumberOfTrees. Functions allow you to decompose your application code into small reusable parts.
>
> The code you see is a **React** app written in the **JavaScript** language. One of todays most used programming languages which can for instance be used to created **Websites, Mobile Apps and APIs**.

## Assignment 2) Styling, make sure the button is according to design.

In the previous assignment you wrote some JavaScript code to implement a certain functionality. In this assignment you will write some CSS code to make sure the buy button looks as the designer intended. Currently it clearly looks out of place.

The design shows the button as follows:

![Buy Button.png](/images/image2.png)

At the bottom of the App.js file you will find the following line of code:

```javascript
const styles = {
  buyButton: {    
  }
}
```

First make sure the text is a bit bigger to improve the readability and better fit in the design. Replace the above lines with the following snippet:

```javascript
const styles = {
  buyButton: {
    fontSize: "28px",
  }
};
```

Notice in your app that the text is now much more readable. You did this by increasing the font size. 

> The font size is specified in **pixels**. In the above code 28px means 28 pixels. Roughly speaking you can say that a pixel is the smallest element in your computer display.

Now let's change the colors of the button. Add the lines with backgroundColor and color to the styling.

```javascript
const styles = {
  buyButton: {
    fontSize: "28px",
    backgroundColor: "#11c174",
    color: "#fff",
  }
};
```

> The colors in CSS are specified using **hexadecimal notation** which means numbers range from 0 to 9, and in addition the characters a - f can also be used. The code specifies components for red, green and blue and can be used to **mix into any color**. You could try changing the background color to `#f00` for a red color, `#0f0` for a green color or `#ff0` for a yellow color.

Now add some more spacing and make the corners of the button slightly rounded.

```javascript
const styles = {
  buyButton: {
    fontSize: "28px",
    backgroundColor: "#11c174",
    color: "#fff",
    paddingLeft: "32px",
    paddingRight: "32px",
    lineHeight: "56px",
    borderRadius: "4px",
  }
};
```

For the finishing touches add the following fields. 

```javascript
const styles = {
  buyButton: {
    fontSize: "28px",
    backgroundColor: "#11c174",
    color: "#fff",
    paddingLeft: "32px",
    paddingRight: "32px",
    lineHeight: "56px",
    borderRadius: "4px",
    fontFamily: "Poppins",
    border: "none",
    cursor: "pointer",
    minWidth: "330px"
  }
};
```

Great. The button now is according to design. You have seen how you can apply styling separately from adding functionality with a language that is designed for this specific purpose.

> The code you have written in this assignment is a Javascript version of the **CSS** language. You can use the language to control all kinds of visual attributes. You have written code to affect text, colors and spacing. Besides this the language can also use to implement animations and make sure that the app renders correctly on both desktops and mobile phones. The latter is called **responsive design** and is implemented using CSS media queries.

## Assignment 3) Fix a bug, make the minus button work correctly.

The users of our app have reported a bug. Apparently there is a problem when the minus button is pressed.

---
*Bug report*: Minus button subtracts two trees instead of one

Steps to reproduce:
- Use the plus button to add trees
- Use the minus button to subtract a tree

Expected behavior: One tree is subtracted
Current behavior: Two trees are subtracted

---

This time we will not provide you with code snippets. Look through the code in App.js and find the function with the name `decreaseNumberOfTrees`. Look through the code there and see if you can spot and fix the bug.

## Assignment 4) Changing requirements, change the iDeal costs.

Recently our payment provider reduced the costs they charge for processing iDeal payments. The price was lowered from €0,34 to €0,29 cents.

Scan through the code in App.js and try to find the lines of code that implement this logic. Change the code to reflect the new price. Note that in JavaScript numbers and amounts always use a dot for the decimal separator.

## Time to plant some trees 🌲🌲🌲
> The app you have worked on today also has an important part you have not seen. It is the API that runs on the **AWS** cloud. The API uses **serverless** technology to make sure the API is **always available and scales automatically**. It is for instance responsible to generate the payment QR code and storing data in a database. The plant a tree api supports both **GraphQL** and **REST** APIs. GraphQL is a popular technique to serve as a communication layer towards web and mobile apps. RESTful APIs are the dominant technique used to integrate systems.

Congratulations. You have a fully functional app that allows you to plant trees. Go ahead, and paint the world green. Plant some trees.

The idea to create and app to plant trees was born at the NN International Hackathon of 2019. Trees are actually planted in a project in Brazil by our partner WeForest. These projects not only help planting trees, but also making sure the trees are allowed to grow. WeForest also promote economic development of local communities to make sure a sustainable environment is created.

Trees cost 2 euros each, and a one time payment processing fee of €0,29 cents. After you press the buy button, you will be presented with a QR code you can scan in your banking app on your mobile phone. As a token of appreciation you will receive a certificate in your email box and a "Plant een boom" sticker.

Thank you for taking this workshop and planting some trees.

## Bonus assignment) Add a +10 button

If you have time left you can work on the bonus assignment. Bringing everything together you learned up to now your assignment is to add one extra button to the app. 

![Add 10 button.png](/images/image3.png)

- Add a +10 button that adds 10 trees at a time
- Make sure to change the button is styled according to design. The background color is `#efefef`. The color is `#333`
- Make sure the existing + button still functions as intended
