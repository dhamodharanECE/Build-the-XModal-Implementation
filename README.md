# 🧩 XModal - Form Validation Application

# 🧾 Overview

XModal is a simple React-based application that demonstrates a modal popup form with data validation.

When the user clicks on the “Open Form” button, a modal appears containing a form that must be filled completely before submission.

It validates:

Required fields (no empty inputs)

Valid email format (@ present)

10-digit phone number

Date of birth not in the future

If any validation fails, the user receives an appropriate alert message or error message beside the respective field.

When all inputs are valid, the form closes automatically and resets to the initial view.

# ✨ Features

✅ Modal popup that opens on button click

✅ Click outside the modal to close it

✅ Real-time validation for all inputs

✅ Alert messages for invalid inputs

✅ Resets to initial view after successful submission

✅ Clean and responsive UI built with pure CSS

# 🖥️ Initial Render

Upon loading the app:

A button labeled “Open Form” is displayed.

The modal is hidden by default.

Example view:

+-------------------------------------+
|           [ Open Form ]             |
+-------------------------------------+

# 📋 Modal Form Behavior

🧍‍♂️ Step 1: Open the Form

When the user clicks on Open Form, the modal appears.

The modal structure:
```
<div className="modal">
  <div className="modal-content">
    <!-- JSX code for form -->
  </div>
</div>
```
# 🧾 Step 2: Form Fields

The form includes these required fields:

Field	Input Type	ID Attribute	Validation Rule
Username	text	username	Cannot be empty
Email	email	email	Must include @ symbol
Phone Number	number	phone	Must be exactly 10 digits
Date of Birth	date	dob	Must not be a future date

The Submit button has the class name:
```
<button className="submit-button">Submit</button>
```
# ⚠️ Validation Rules and Alert Messages

Validation Case	Behavior / Message

Empty field	Show a message beside the field: “Please fill out this field.”

Invalid email (missing “@”)	alert("Invalid email. Please check your email address.")

Invalid phone number (not 10 digits)	alert("Invalid phone number. Please enter a 10-digit phone number.")

Future date of birth	alert("Invalid date of birth. Please enter a valid past date.")

# ✅ Successful Submission

If all the fields are filled correctly:

The form modal closes automatically.

The app returns to the initial render state.

The inputs reset to blank.

# 🖱️ Modal Close Behavior

If the modal is open and the user clicks outside the modal, the modal will automatically close, showing the initial “Open Form” button again.

# 🧱 Required Structure

Make sure the following structure and class names are used (as per test case requirements):
```
<div className="modal">
  <div className="modal-content">
    <form>
      <input id="username" type="text" />
      <input id="email" type="email" />
      <input id="phone" type="number" />
      <input id="dob" type="date" />
      <button className="submit-button">Submit</button>
    </form>
  </div>
</div>
```
# 🧠 Implementation Logic
```
Open/Close Modal:
const [showModal, setShowModal] = useState(false);


Clicking the Open Form button → setShowModal(true)

Clicking outside modal → setShowModal(false)

Form Validation:
const handleSubmit = (e) => {
  e.preventDefault();

  if (!username || !email || !phone || !dob) {
    alert("Please fill all fields");
    return;
  }

  if (!email.includes("@")) {
    alert("Invalid email. Please check your email address.");
    return;
  }

  if (phone.length !== 10) {
    alert("Invalid phone number. Please enter a 10-digit phone number.");
    return;
  }

  const today = new Date();
  if (new Date(dob) > today) {
    alert("Invalid date of birth. Please enter a valid past date.");
    return;
  }

  // If all validations pass
  setShowModal(false);
  alert("Form submitted successfully!");
};
```
# ⚙️ Tech Stack

Technology	Purpose

ReactJS	UI development and state management

HTML5	Form structure

CSS3 (Flexbox)	Modal styling and layout

JavaScript (ES6)	Input validation and event handling

# 🚀 Installation and Setup

Clone the Repository
```
git clone https://github.com/dhamodharanECE/Build-the-XModal-Implementation.git
```
cd Project

Install Dependencies
```
npm install
```
Run the Project
```
npm start
```
View in Browser
```
http://localhost:3000
```
# 🧠 Learnings

Handling form input with React state

Performing form validation in React

Creating a modal component using conditional rendering

Implementing click outside detection

Styling with pure CSS and Flexbox

# 📸 UI Preview:

# Open-Model:

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/70f5a867-39ad-41d8-b97a-e0718eaf4249" />

# Login Form:

<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/ad5d2731-bf96-45cd-bedd-4ec226c37140" />

# Deployment Link:
```base
https://build-the-x-modal-implementation-ch.vercel.app/
