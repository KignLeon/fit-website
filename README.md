Contemporary Technologic Institute (CTI) Website
Project Version: 1.0.0

Once the server has started, open a web browser and navigate to:
http://localhost:8080

Last Updated: July 31, 2025

1. Project Overview

This repository contains the source code for the official website of the Contemporary Technologic Institute (CTI). The project is a modern, 3-page informational and enrollment website designed to be robust, scalable, and easy to maintain.

The application is built using a classic full-stack architecture, with a Java backend serving a static HTML, CSS, and JavaScript frontend. This provides a clear separation of concerns between the server-side logic and the client-side user experience.

The primary goals of this website are:

- To clearly present CTI's mission and services.

- To provide a seamless enrollment and consultation request process for prospective clients.

- To serve as a professional and trustworthy online presence for the institute.

2. Technology Stack

The project leverages a curated set of technologies chosen for their stability and industry-standard status.

Backend:

Java: The core programming language for the server.

SparkJava: A lightweight, micro-framework used to create the web server and define API endpoints (routes). It handles incoming HTTP requests.

Maven: The project management and build tool. It manages dependencies (libraries) and packages the application for deployment.

SLF4J: A logging facade used for structured, professional logging of server-side events and errors.

Frontend:

HTML5: Provides the structure and content for all web pages.

Tailwind CSS: A utility-first CSS framework used for all styling. It allows for rapid, responsive, and consistent UI development directly within the HTML.

JavaScript (ES6+): Used for client-side interactivity, primarily for handling the enrollment form submission without a page reload (asynchronous request).

3. Project Structure

The project follows the Standard Directory Layout for Maven, which keeps the source code organized and predictable.

cti-website/
├── .vscode/            # VS Code editor settings (optional)
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── cti/
│   │   │           └── Main.java       # <-- The Java Backend Server
│   │   └── resources/
│   │       └── public/                 # <-- The root for all frontend files
│   │           ├── css/
│   │           │   └── style.css       # Custom CSS styles
│   │           ├── js/
│   │           │   └── script.js       # Client-side JavaScript
│   │           ├── about.html          # The 'About' page
│   │           ├── enroll.html         # The 'Enrollment' page
│   │           └── index.html          # The Homepage
│   └── test/                           # (Currently unused)
├── pom.xml                             # <-- The Maven "Blueprint"
└── README.md                           # This documentation file

4. File Breakdown

Each file in this project has a distinct and important role.

Backend Files

pom.xml

Purpose: The "Project Object Model." This is the core configuration file for Maven.

Function: It defines project information (like its name), lists all required external libraries (dependencies like SparkJava and Gson), and specifies how to build and package the application into a runnable JAR file.

src/main/java/com/cti/Main.java

Purpose: The main entry point and heart of the backend application.

Function:

It initializes and configures the SparkJava web server.

It tells the server to serve all static files (HTML, CSS, JS) from the src/main/resources/public directory.

It defines the /enroll API endpoint. When the frontend sends a POST request to this URL, this file contains the code to receive the data, log it to the console, and send back a success or error response.

Frontend Files

src/main/resources/public/ (The "Public" Folder)

Purpose: This directory is the web root. When the Java server is running, anything in this folder is publicly accessible from the browser.

index.html, enroll.html, about.html

Purpose: These are the three pages of the website.

Function: They define the content and structure of the site using standard HTML. They link to the Tailwind CSS CDN for styling and to the local script.js file for interactivity.

css/style.css

Purpose: A placeholder for any custom CSS styles.

Function: While nearly all styling is handled by Tailwind CSS classes in the HTML, this file can be used for complex animations or overrides that don't fit the utility-first model.

js/script.js

Purpose: Handles all client-side dynamic behavior.

Function: It listens for the "submit" event on the enrollment form. When submitted, it prevents the page from reloading, collects the form data, converts it to JSON, and sends it to the /enroll endpoint on the Java backend using the Fetch API. It then displays a success or error message to the user based on the server's response.

5. How to Set Up and Run the Project

To run this project on a local machine, ensure you have Java (JDK 17+) and Maven installed.

Clone the Repository:

git clone <repository-url>
cd cti-website

Build the Project with Maven:
Open a terminal in the cti-website root directory and run the following command. This will download all the necessary dependencies.

mvn clean install

Run the Application:
You can run the application directly from your IDE (like VS Code or IntelliJ) by running the main method in Main.java. Alternatively, you can run the packaged application from the terminal:

java -jar target/cti-website-1.0-SNAPSHOT.jar

Access the Website:
Once the server has started, open a web browser and navigate to:
http://localhost:8080

You should now see the CTI homepage and be able to interact with the full website.

