HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Box Model Inspection</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Header Section -->
    <header>
        <h1>CSS Box Model Inspection</h1>
        <p>Exploring content, padding, border, margin, and box-sizing properties.</p>
    </header>

    <main class="box-container">
        <!-- Box 1 -->
        <div class="box box-1">
            <h2>Box One</h2>
            <p>This box has custom padding, a solid border, and standard margins.</p>
        </div>

        <!-- Box 2 -->
        <div class="box box-2">
            <h2>Box Two</h2>
            <p>This box features different padding, a thick dashed border, and larger vertical margins.</p>
        </div>

        <!-- Box 3 (Content-Box vs Border-Box) -->
        <div class="box box-3">
            <h2>Box Three</h2>
            <p>This box explicitly uses <code>box-sizing: content-box</code> to demonstrate width expansion.</p>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 Web Development Practice</p>
    </footer>

</body>
</html>

CSS
/* Global Reset */
* {
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f4f6f9;
    color: #333333;
    padding: 20px;
}

header {
    text-align: center;
    margin-bottom: 30px;
}

.box-container {
    max-width: 600px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

/* Box 1: Standard Border-Box layout */
.box-1 {
    background-color: #ffffff;
    padding: 15px;
    border: 3px solid #3498db;
    margin: 10px 0;
    box-sizing: border-box; /* Width includes padding and border */
}

/* Box 2: Larger padding and dashed border */
.box-2 {
    background-color: #ffffff;
    padding: 25px;
    border: 4px dashed #e74c3c;
    margin: 20px 0;
    box-sizing: border-box;
}

/* Box 3: Content-Box demonstration */
.box-3 {
    background-color: #ffffff;
    padding: 30px;
    border: 5px solid #2ecc71;
    margin: 15px 0;
    box-sizing: content-box; /* Width applies ONLY to content; padding and borders add to total size */
    width: 400px; 
}

h2 {
    color: #2c3e50;
    margin-bottom: 8px;
}

footer {
    text-align: center;
    margin-top: 40px;
    color: #7f8c8d;
    font-size: 0.9rem;
}

How to Inspect in Chrome DevTools:

Open your project in the browser using Live Server.

Right-click any box and select Inspect.

In the Elements panel, make sure the Styles tab is active, then scroll down to the bottom of the right-hand sidebar to view the interactive Box Model diagram.

Explanation of Box Model Layers 

Content: The innermost layer where text ("Box One", paragraph) and images live.

Padding: The transparent inner space clearing area directly surrounding the content, located inside the border.

Border: The structural line wrapping around the padding and content layers.

Margin: The outermost transparent spacing separating the element from neighboring elements on the page.

content-box vs border-box Difference:

box-sizing: border-box (Boxes 1 & 2): Width and height include the content, padding, and border. If you set a width of 300px, the total physical width on screen remains exactly 300px.

box-sizing: content-box (Box 3): Width applies only to the content area. Padding and borders are added on top of that width, making the total element wider than specified.
