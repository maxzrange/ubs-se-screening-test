# Backend Engineer Technical Assessment

Thank you for your interest in joining our team! This technical assessment is designed to evaluate your skills in Go, API development, and React. It consists of two parts: a set of theoretical questions and a practical coding challenge.

Please take your time and aim for quality, clarity, and correctness. The task is designed to take approximately 3-4 hours to complete.
To give you flexibility, please submit your solution within 24 hours. If you have any significant time constraints, just let us know.


---

## Part 1: Theoretical Questions

Please answer the following questions in a simple text or markdown file (e.g., `answers.md`) inside your repository.

1.  **Go Concurrency:** In Go, what is the difference between a `goroutine` and a standard OS thread? Briefly describe a scenario where you would use the `select` statement with channels.
2.  **API Design:** You need to add a new, breaking feature to a production API that is already being used by customers. What is a common strategy to introduce this change without disrupting existing users?
3.  **Database:** Imagine a table `users` and a table `orders`, where each order has a `user_id`. How would you write a SQL query to get the names of all users who have placed at least one order? What kind of database index would speed up this query?
4.  **PDF Generation:** What are the main challenges you might face when generating very large or complex PDF files (e.g., a 500-page report with many tables and images) on a server?

---

## Part 2: Practical Coding Challenge

### Objective
Create a simple web service for a **Utility Billing System (UBS)** that generates a PDF invoice on demand.

### Scenario
A customer service agent needs to generate a simple utility bill for a customer. Your task is to build the backend API for this and a minimal frontend to interact with it.

### Backend Requirements (Go)

-   Create a single HTTP API endpoint: `POST /generate-invoice`.
-   The endpoint must accept a JSON payload with the following structure:
    ```json
    {
      "customer_name": "John Doe",
      "address": "123 Power Lane, Electric City",
      "items": [
        {"description": "Electricity Usage (kWh)", "quantity": 350, "unit_price": 0.15},
        {"description": "Water Usage (m³)", "quantity": 12, "unit_price": 2.50},
        {"description": "Service Fee", "quantity": 1, "unit_price": 10.00}
      ]
    }
    ```
-   Upon receiving the request, the Go service must:
    1.  Calculate the total amount for each item (`quantity` * `unit_price`).
    2.  Calculate the final grand total for the invoice.
    3.  Generate a simple PDF document containing the customer's name, address, a table of the items with their totals, and the grand total.
    4.  Return the generated PDF file in the HTTP response with the correct `Content-Type` header (`application/pdf`).
    5.  Please include unit tests for the core business logic (e.g., the functions that calculate item totals and the grand total).
-   **Recommendation:** Use a standard library for the web server and a well-known library for PDF generation (e.g., `chromedp`, gofpdf` or `unidoc`).

### Frontend Requirements (React)

-   Create a single-page application with a simple form.
-   The form should have fields to input the customer's name, address, and a dynamic list of items (description, quantity, unit price).
-   When the "Generate PDF" button is clicked, the frontend should:
    1.  Send the form data as a JSON payload to your Go backend API.
    2.  Receive the PDF response from the API and trigger a file download in the user's browser.
-   **Recommendation:** You can use a simple UI component library like **Mantine UI** or **Shadcn/UI** if you wish, but it is not required. The main focus is on functionality.

---

## Submission Instructions

1.  Click the green **"Use this template"** button at the top of this page and select **"Create a new repository"**.
2.  Name your repository (e.g., `[YourName]-backend-test`).
3.  **IMPORTANT:** Set the repository visibility to **PRIVATE**. This is a critical step to ensure your work remains your own. Do not fork this repository.
4.  Add your answers to the theoretical questions and the complete source code for the coding challenge to your new repository.
5.  Include a `README.md` file in your project with clear, step-by-step instructions on how to run your application.
6.  Once you have completed the test, invite the hiring manager **`https://github.com/ariefitriadin`** as a collaborator to your private repository.
7.  Finally, email the link to your repository back to our HR team.

Good luck! We look forward to seeing your submission.
