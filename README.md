<!DOCTYPE html>
<html>
<head>
    <title>Reminder Application</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            width: 300px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-shadow: 0 0 5px #aaa;
        }
        #welcomePage, #setReminderPage {
            display: none;
        }
    </style>
</head>
<body>
    <div id="loginPage" class="container">
        <h2>Login</h2>
        <form id="loginForm">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required><br><br>
            
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required><br><br>
            
            <input type="submit" value="Login">
        </form>
    </div>

    <div id="welcomePage" class="container">
        <h2>Welcome to the Reminder Application <span id="loggedInUsername"></span></h2>
        <p>Today is Tuesday,14th of February</p>
        <ul>
            <li>Set Reminder</li>
            <li>Modify Reminder</li>
            <li>Disable Reminder</li>
            <li>Delete Reminder</li>
            <li>Enable Reminder</li>
            <li>View your Reminders</li>
        </ul>
        <button id="logout">Log out</button>
    </div>

    <div id="setReminderPage" class="container">
        <h2>Set a New Reminder</h2>
        <form id="reminderForm">
            <label for="date">Select a Date:</label>
            <input type="date" id="date" name="date" required><br><br>

            <label for="subject">Subject:</label>
            <select id="subject" name="subject" required>
                <option value="subject1">Subject 1</option>
                <option value="subject2">Subject 2</option>
                <option value="subject3">Subject 3</option>
            </select><br><br>

            <label for="description">Add Description:</label>
            <textarea id="description" name="description" rows="4" required></textarea><br><br>

            <label for="email">Email Address:</label>
            <input type="email" id="email" name="email" required><br><br>

            <label for="contactNo">Contact No:</label>
            <input type="tel" id="contactNo" name="contactNo"><br><br>

            <label for="smsNo">SMS No:</label>
            <input type="tel" id="smsNo" name="smsNo"><br><br>

            <label>Recur for Next:</label><br>
            <input type="checkbox" name="recur" value="7 Days"> 7 Days
            <input type="checkbox" name="recur" value="5 Days"> 5 Days
            <input type="checkbox" name="recur" value="3 Days"> 3 Days
            <input type="checkbox" name="recur" value="2 Days"> 2 Days<br><br>

            <input type="submit" value="Set Reminder">
        </form>
        <button id="confirmBack">Confirm</button>
    </div>

    <script>
        document.getElementById("loginForm").addEventListener("submit", function(event) {
            event.preventDefault();
            const username = "Text box";
            const password = "Textbox";
            const enteredUsername = document.getElementById("username").value;
            const enteredPassword = document.getElementById("password").value;
            
            if (enteredUsername === username && enteredPassword === password) {
                // Successful login
                document.getElementById("loginPage").style.display = "none";
                document.getElementById("welcomePage").style.display = "block";
                document.getElementById("loggedInUsername").textContent = username;
            } else {
                alert("Invalid username or password. Please try again.");
            }
        });

        document.getElementById("logout").addEventListener("click", function() {
            // Log out and show the login form again
            document.getElementById("loginPage").style.display = "block";
            document.getElementById("welcomePage").style.display = "none";
            document.getElementById("setReminderPage").style.display = "none";
            document.getElementById("username").value = "";
            document.getElementById("password").value = "";
        });

        document.getElementById("welcomePage").addEventListener("click", function() {
            // Show the set reminder page
            document.getElementById("welcomePage").style.display = "none";
            document.getElementById("setReminderPage").style.display = "block";
        });

        document.getElementById("confirmBack").addEventListener("click", function() {
            // Show the welcome page
            document.getElementById("setReminderPage").style.display = "none";
            document.getElementById("welcomePage").style.display = "block";
        });
    </script>
</body>
</html>
