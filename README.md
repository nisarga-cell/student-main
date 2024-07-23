# student-main

Superviser This project was supervised by Victor Ikechukwu Agughasi.



To create a `README.md` file that describes the HTML form and the steps to ensure no negative numbers can be entered in the form fields, you can use the following content:

```markdown
# Student Performance Prediction Form

This project contains an HTML form designed to collect student information for predicting their performance. The form includes fields for gender, race/ethnicity, parental level of education, math score, reading score, writing score, lunch type, and test preparation course. 

The form ensures that negative numbers cannot be entered for the score fields (math, reading, and writing).

## Features

- HTML5 form with various input fields
- Validation to prevent negative numbers for scores
- Responsive and visually appealing design

## Form Structure

### HTML

The form consists of the following sections:

1. **Gender**: A dropdown to select the gender of the student.
2. **Race/Ethnicity**: A dropdown to select the race/ethnicity of the student.
3. **Parental Level of Education**: A dropdown to select the parental level of education.
4. **Math Score**: An input field to enter the math score. It only accepts non-negative numbers.
5. **Reading Score**: An input field to enter the reading score. It only accepts non-negative numbers.
6. **Writing Score**: An input field to enter the writing score. It only accepts non-negative numbers.
7. **Lunch**: A dropdown to select the type of lunch.
8. **Test Preparation Course**: A dropdown to select if the test preparation course was completed or not.

### CSS

The form includes custom styles to make it visually appealing and responsive.

## Implementation

### HTML Code

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Performance Prediction Form</title>
</head>

<body>

    <form class="app" method="POST" action="/predict">
        <div id="final_price">
            performance score: {{ Average }}
        </div>

        <div class="table">

            <div class="wrap">
                <div class="col">Gender</div>
                <div class="value">
                    <select name="Gender" id="Gender">
                        <option value="Female">Female</option>
                        <option value="Male">Male</option>
                    </select>
                </div>
            </div>

            <div class="wrap">
                <div class="col">Race/ethnicity</div>
                <div class="value">
                    <select name="Race/ethnicity" id="Race/ethnicity">
                        <option value="Group A">Group A</option>
                        <option value="Group B">Group B</option>
                        <option value="Group C">Group C</option>
                        <option value="Group D">Group D</option>
                        <option value="Group E">Group E</option>
                    </select>
                </div>
            </div>

            <div class="wrap">
                <div class="col">Parental Level of Education</div>
                <div class="value">
                    <select name="Parental_Level_of_Education" id="Parental_Level_of_Education">
                        <option value="some high school">Some High School</option>
                        <option value="high school">High School</option>
                        <option value="associate's degree">Associate's Degree</option>
                        <option value="master's degree">Master's Degree</option>
                        <option value="some college">Some College</option>
                        <option value="bachelor's degree">Bachelor's Degree</option>
                    </select>
                </div>
            </div>

            <div class="wrap">
                <div class="col">Math Score</div>
                <div class="value">
                    <input type="number" name="Math_Score" min="0" required="required">
                </div>
            </div>

            <div class="wrap">
                <div class="col">Reading Score</div>
                <div class="value">
                    <input type="number" name="Reading_score" min="0" required="required">
                </div>
            </div>

            <div class="wrap">
                <div class="col">Writing Score</div>
                <div class="value">
                    <input type="number" name="Writing_score" min="0" required="required">
                </div>
            </div>

            <div class="wrap">
                <div class="col">Lunch</div>
                <div class="value">
                    <select name="Lunch" id="Lunch">
                        <option value="standard">Standard</option>
                        <option value="free/reduced">Free/Reduced</option>
                    </select>
                </div>
            </div>

            <div class="wrap">
                <div class="col">Test Preparation Course</div>
                <div class="value">
                    <select name="test_preparation_course" id="test_preparation_course">
                        <option value="None">None</option>
                        <option value="Completed">Completed</option>
                    </select>
                </div>
            </div>

        </div>
        <button class="submitBtn" type="submit">Submit</button>
    </form>

</body>

<style>
    body {
        margin: 0;
        padding: 0;
        height: 100vh;
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }

    .app {
        background-image: url("{{url_for('static', filename='images_score.png')}}"),
        repeating-linear-gradient(45deg, rgb(83, 83, 83) 0px, rgb(83, 83, 83) 50px, rgb(124, 124, 124) 50px, rgb(124, 124, 124) 100px);
        background-repeat: no-repeat;
        background-size: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        flex-flow: column nowrap;
    }

    .table {
        backdrop-filter: blur(4px);
        padding: 2em 1em;
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.3);
        border-radius: 5px;
        width: 80vw;
        display: flex;
        flex-flow: row wrap;
        justify-content: space-around;
        position: relative;
        top: 10vw;
    }

    .wrap {
        margin: 0.5em;
        width: calc(33.33% - 2em);
        display: flex;
        flex-flow: column nowrap;
        justify-content: space-between;
    }

    .wrap .col {
        text-align: center;
        font-size: 1em;
        padding-bottom: 0.5em;
        color: white;
        text-transform: uppercase;
        word-wrap: break-word;
    }

    .value input,
    .value select {
        width: 100%;
        font-size: 1.2em;
        border: none;
        backdrop-filter: blur(4px);
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.4);
        background: none;
        color: whitesmoke;
        padding: 0.25em 0.5em;
        text-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
    }

    .value select option {
        background: rgba(0, 0, 0, 0.3);
        color: whitesmoke;
    }

    .submitBtn {
        position: relative;
        top: 10vw;
        margin-top: 1em;
        background: rgba(0, 0, 0, 0.3);
        color: whitesmoke;
        padding: 0.5em 2em;
        font-size: 1.5em;
        text-transform: uppercase;
        border: none;
    }

    #final_price {
        color: red;
        font-size: x-large;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        border: solid;
        border-radius: 10px;
        width: 230px;
        height: 90px;
        text-align: left;
        padding: 12px;
        background-color: black;
    }
</style>

</html>
```

## CSS Code

The CSS code provides the styling for the form, ensuring it is responsive and visually appealing.

### Additional Notes

- Ensure that your server-side validation also checks for non-negative numbers to maintain data integrity.
- This form uses `{{url_for('static', filename='images_score.png')}}` for the background image, which is a Jinja2 template expression commonly used in Flask applications to serve static files.

## Running the Application

To run the application:

1. Make sure you have a server set up to handle the form submission.
2. Place the HTML code in an appropriate file (e.g., `index.html`) and ensure it is served by your web server.
3. Ensure that your server-side script (e.g., a Flask route) processes the form data correctly.

### Flask Example

```python
from flask import Flask, render_template,

 request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html', Average=85)  # Replace 85 with your actual average calculation

@app.route('/predict', methods=['POST'])
def predict():
    # Handle form data
    gender = request.form['Gender']
    race = request.form['Race/ethnicity']
    education = request.form['Parental_Level_of_Education']
    math_score = request.form['Math_Score']
    reading_score = request.form['Reading_score']
    writing_score = request.form['Writing_score']
    lunch = request.form['Lunch']
    prep_course = request.form['test_preparation_course']
    
    # Your prediction logic here

    return 'Form submitted successfully'

if __name__ == '__main__':
    app.run(debug=True)
```

This `README.md` provides an overview of the form, its structure, the validation implemented to prevent negative numbers, and instructions on how to set up and run the application.
![Screenshot 2024-07-23 140932](https://github.com/user-attachments/assets/00e07dab-8b92-4364-8879-14ff98be7f42)


