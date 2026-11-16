# EX01 Developing a Simple Webserver
## Date: 16-11-2026
## REG NO: 26010852

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
rom http.server import HTTPServer, BaseHTTPRequestHandler

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Development Frameworks</title>

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Materialize CSS -->
    <link rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">

    <!-- Vue.js -->
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

    <!-- React -->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <!-- Babel for JSX -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <!-- jQuery -->
    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f4f6f9;
            margin: 0;
        }

        header {
            background: #172554;
            color: white;
            text-align: center;
            padding: 30px;
        }

        nav {
            background: #1e293b;
            padding: 15px;
            text-align: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            margin: 10px;
            display: inline-block;
        }

        section {
            background: white;
            padding: 25px;
            margin: 25px auto;
            max-width: 1000px;
            border-radius: 12px;
            box-shadow: 0 3px 10px #ddd;
        }

        button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        footer {
            text-align: center;
            background: #172554;
            color: white;
            padding: 20px;
        }
    </style>
</head>

<body>

<header>
    <h1>Web Development Frameworks</h1>
    <p>Learn different frameworks and libraries in one webpage</p>
</header>

<nav>
    <a href="#html">HTML</a>
    <a href="#bootstrap">Bootstrap</a>
    <a href="#tailwind">Tailwind</a>
    <a href="#react">React</a>
    <a href="#angular">Angular</a>
    <a href="#vue">Vue</a>
    <a href="#jquery">jQuery</a>
    <a href="#materialize">Materialize</a>
</nav>

<!-- 1. HTML -->
<section id="html">
    <h2>1. HTML</h2>
    <p>HTML is used to create the structure of webpages.</p>

    <h3>Welcome to HTML</h3>
    <p>This is a basic HTML example.</p>

    <button onclick="alert('Hello HTML!')">
        Click Me
    </button>
</section>

<!-- 2. Bootstrap -->
<section id="bootstrap">
    <h2>2. Bootstrap</h2>
    <p>Bootstrap is a responsive CSS framework.</p>

    <div class="container bg-light p-4">
        <h3 class="text-primary">Bootstrap Example</h3>
        <p class="lead">Create responsive websites easily.</p>

        <button class="btn btn-success"
        onclick="alert('Hello Bootstrap!')">
            Bootstrap Button
        </button>
    </div>
</section>

<!-- 3. Tailwind CSS -->
<section id="tailwind">
    <h2>3. Tailwind CSS</h2>
    <p>Tailwind uses utility classes for styling.</p>

    <div class="bg-blue-100 p-5 rounded-xl text-center">
        <h3 class="text-3xl font-bold text-blue-700">
            Welcome to Tailwind
        </h3>

        <p class="text-gray-700 mt-3">
            Build modern websites using utility classes.
        </p>

        <button
        class="bg-blue-600 text-white rounded-lg px-5 py-2 mt-3"
        onclick="alert('Hello Tailwind!')">
            Tailwind Button
        </button>
    </div>
</section>

<!-- 4. React -->
<section id="react">
    <h2>4. React.js</h2>
    <p>React is used to create interactive user interfaces.</p>

    <div id="react-root"></div>

    <script type="text/babel">
        function ReactExample() {
            const [message, setMessage] =
                React.useState("Welcome to React!");

            return (
                <div>
                    <h3>{message}</h3>
                    <button
                        style={{
                            background: "#61dafb",
                            color: "#000"
                        }}
                        onClick={() =>
                            setMessage("Hello React!")
                        }>
                        React Button
                    </button>
                </div>
            );
        }

        ReactDOM.createRoot(
            document.getElementById("react-root")
        ).render(<ReactExample />);
    </script>
</section>

<!-- 5. Angular -->
<section id="angular">
    <h2>5. Angular</h2>
    <p>Angular is a TypeScript-based web application framework.</p>

    <h3>Angular Example</h3>
    <p>{{ angularMessage }}</p>

    <button onclick="showAngular()"
    style="background:#dd0031;color:white;">
        Angular Button
    </button>
</section>

<script>
    function showAngular() {
        document.getElementById("angular").querySelector("p:nth-of-type(2)")
            .innerText = "Hello Angular!";
    }
</script>

<!-- 6. Vue.js -->
<section id="vue">
    <h2>6. Vue.js</h2>
    <p>Vue is a progressive JavaScript framework.</p>

    <div id="vue-app">
        <h3>{{ message }}</h3>

        <button
        style="background:#42b883;color:white;"
        @click="changeMessage">
            Vue Button
        </button>
    </div>
</section>

<script>
    Vue.createApp({
        data() {
            return {
                message: "Welcome to Vue.js!"
            };
        },
        methods: {
            changeMessage() {
                this.message = "Hello Vue.js!";
            }
        }
    }).mount("#vue-app");
</script>

<!-- 7. jQuery -->
<section id="jquery">
    <h2>7. jQuery</h2>
    <p>jQuery simplifies JavaScript and HTML manipulation.</p>

    <h3 id="jquery-message">Welcome to jQuery!</h3>

    <button id="jquery-button"
    style="background:#0769ad;color:white;">
        jQuery Button
    </button>
</section>

<script>
    $(document).ready(function() {
        $("#jquery-button").click(function() {
            $("#jquery-message").text("Hello jQuery!");
        });
    });
</script>

<!-- 8. Materialize CSS -->
<section id="materialize">
    <h2>8. Materialize CSS</h2>
    <p>Materialize is based on Google's Material Design.</p>

    <div class="card-panel teal lighten-2 white-text">
        <h4>Welcome to Materialize</h4>
        <p>Create beautiful web interfaces.</p>
    </div>

    <button class="btn waves-effect waves-light"
    onclick="alert('Hello Materialize!')">
        Materialize Button
    </button>
</section>

<footer>
    <p>Web Development Frameworks</p>
    <p>HTML | CSS | JavaScript | Bootstrap | React | Angular | Vue</p>
    <p>© 2026 All Rights Reserved</p>
</footer>

</body>
</html>
'''

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()

## OUTPUT:
<img width="1920" height="1080" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/b148ae2c-2d0d-47f8-96c5-517e98279f3f" />
<img width="1920" height="1080" alt="Screenshot (24)" src="https://github.com/user-attachments/assets/8c5ae188-e7dc-4114-bdf6-93786502792f" />
<img width="1920" height="1080" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/331f88b8-1f4c-4b57-8509-d80983200aca" />
<img width="1920" height="1080" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/b9037acb-67c6-48e7-8639-23f2b7919160" />
<img width="774" height="301" alt="Screenshot 2026-11-16 084041" src="https://github.com/user-attachments/assets/1cb70290-07de-4b1b-a89f-c9db7f25092d" />

## RESULT:
The program for implementing simple webserver is executed successfully.
