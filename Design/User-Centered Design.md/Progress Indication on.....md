# What Are Best Practices for Progress Indication on Forms, Registration, and Setup?

## Introduction

> **NOTE:** Some of the interactive examples use CSS and JavaScript concepts you may not have learned yet. Don't worry about understanding every line of code. The examples are meant to demonstrate the design concepts and provide a visual preview of how progress indicators work.

## What is Progress Indication?

**Progress indication** is a way to show users how far they are in a process. It is commonly used in:

- Forms
- Registration processes
- Account setup
- Multi-step applications
- Checkout processes

The goal is to help users understand:

- Where they are in the process.
- How much they have completed.
- How much remains before they finish.

This makes the experience more transparent and reduces uncertainty.

---

## Why is Progress Indication Important?

Imagine asking users to complete a long form without telling them how many steps remain.

Users may ask themselves:

- "How much longer is this?"
- "Do I have enough time to finish?"
- "Should I continue now or come back later?"

A progress indicator answers these questions by showing the user's current progress.

This transparency helps users decide whether they can finish the process now or return later.

---

# Example: Multi-Step Form with Progress Bar

The following example demonstrates a multi-step form that updates a progress bar and step number as the user moves through each section.

## HTML

```html
<form id="multiStepForm">
  <div class="form-progress">
    <label class="progress-label">Form progress</label>

    <div class="progress-container">
      <div class="progress-bar"></div>
      <div class="progress-text">
        Step 1 of 3
      </div>
    </div>
  </div>

  <!-- Step 1 -->
  <fieldset class="form-step active">
    <legend>Personal Information</legend>

    <label for="name">Full Name:</label>
    <input
      type="text"
      id="name"
      required
    >

    <label for="email">Email:</label>
    <input
      type="email"
      id="email"
      required
    >

    <button
      type="button"
      class="next-btn"
    >
      Next
    </button>
  </fieldset>

  <!-- Step 2 -->
  <fieldset class="form-step">
    <legend>Address</legend>

    <label for="address">
      Street Address:
    </label>

    <input
      type="text"
      id="address"
      required
    >

    <label for="city">City:</label>

    <input
      type="text"
      id="city"
      required
    >

    <button
      type="button"
      class="prev-btn"
    >
      Previous
    </button>

    <button
      type="button"
      class="next-btn"
    >
      Next
    </button>
  </fieldset>

  <!-- Step 3 -->
  <fieldset class="form-step">
    <legend>Review & Submit</legend>

    <p>
      Please review your
      information before
      submitting.
    </p>

    <button
      type="button"
      class="prev-btn"
    >
      Previous
    </button>

    <button type="submit">
      Submit
    </button>
  </fieldset>
</form>
```

## CSS

```css
.form-progress {
  max-width: 500px;
  margin: 20px auto 30px;
}

.progress-container {
  position: relative;
  background: #555;
  height: 30px;
  border-radius: 8px;
  overflow: hidden;
}

.progress-bar {
  background: #4caf50;
  width: 0;
  height: 100%;
  transition: width .3s;
}

.progress-text {
  position: absolute;
  width: 100%;
  text-align: center;
  line-height: 30px;
  color: white;
}

.form-step {
  display: none;
}

.form-step.active {
  display: block;
}
```

## JavaScript

```javascript
const form =
document.getElementById(
"multiStepForm"
);

const steps =
form.querySelectorAll(
".form-step"
);

const progressBar =
form.querySelector(
".progress-bar"
);

const progressText =
form.querySelector(
".progress-text"
);

let currentStep = 0;
const totalSteps =
steps.length;

function updateProgress() {

  const percent =
  ((currentStep + 1)
  / totalSteps) * 100;

  progressBar.style.width =
  percent + "%";

  progressText.textContent =
  `Step ${currentStep + 1}
   of ${totalSteps}`;
}

function showStep(index) {

  steps.forEach(
  (step, i) => {

    step.classList.toggle(
      "active",
      i === index
    );

  });

  updateProgress();
}

showStep(currentStep);
```

---

## How This Example Works

The form is divided into **three smaller steps** instead of presenting every input field on one long page.

As the user clicks **Next** or **Previous**:

- The current section changes.
- The progress bar updates.
- The step number changes.
- The user always knows their current position.

Instead of seeing one long form, users experience smaller, manageable sections.

---

## Benefits of Multi-Step Forms

Breaking a large form into smaller sections:

- Makes forms less intimidating.
- Helps users focus on one task at a time.
- Improves completion rates.
- Makes progress easier to understand.
- Creates a smoother user experience.

---

## Progress Indicators Can Display

A progress indicator can show:

- A progress bar.
- Current step.
- Total number of steps.
- Percentage completed.

Example:

```text
Step 1 of 3

████████░░░░░░░░░

33%
```

As users continue, the indicator updates automatically.

---

# Best Practices for Designing Progress Indicators

When designing a progress indication section, there are a few best practices to keep in mind.

---

## 1. Keep It Simple

The first consideration is to **keep it simple**.

You don't want to overwhelm users with too much information. If the progress indicator is cluttered or difficult to understand, users may become frustrated and leave the site before completing the process.

A good progress indicator should be:

- Easy to understand.
- Easy to read.
- Visually clear.
- Focused on showing only the necessary information.

---

## 2. Allow Users to Go Back

The second consideration is to make it possible for users to **go back to previous steps**.

This is important because users may want to:

- Review their previous answers.
- Correct mistakes.
- Update information before submitting.

Providing **Previous** and **Next** buttons gives users more control over the process and improves the overall user experience.

---

## 3. Make the Progress Indicator Easy to Find

Another consideration is to make the progress indication section **easy to find**.

If users cannot quickly locate the progress indicator, they won't know:

- How far they have progressed.
- How many steps remain.
- Whether they are almost finished.

The progress indicator should be placed where it is clearly visible throughout the process.

---

## 4. Use Clear Section Titles, Steps, and Percentages

The last consideration is to provide clear context for the progress indicator.

A progress bar by itself is not enough.

Users should also see information such as:

- Section titles.
- Step numbers.
- Completion percentages.

For example:

```text
Step 2 of 4 (50%)

██████████░░░░░░░░
```

This tells users:

- Their current step.
- The total number of steps.
- Their percentage of completion.

Without this context, users may not understand what the progress bar represents.

---

# Accessibility Improvements

The second example in the lesson improves the progress indicator by adding accessibility features and more detailed progress information.

Instead of only displaying a progress bar, it also includes:

- Current step number.
- Total number of steps.
- Completion percentage.
- ARIA attributes for screen readers.

Example:

```html
<div
  class="progress-container"
  role="progressbar"
  aria-valuemin="0"
  aria-valuemax="100"
  aria-valuenow="25"
>
```

### Purpose of Each Attribute

| Attribute | Purpose |
|-----------|---------|
| `role="progressbar"` | Identifies the element as a progress bar. |
| `aria-valuemin="0"` | Defines the minimum progress value. |
| `aria-valuemax="100"` | Defines the maximum progress value. |
| `aria-valuenow="25"` | Indicates the user's current progress. |

These attributes allow assistive technologies, such as screen readers, to accurately announce the user's progress.

---

## Additional Information Displayed

The improved example also displays information like:

```text
Step 1 of 4 (25%)
```

This provides users with both numerical and visual feedback.

---

# Why Progress Indicators Improve User Experience

Progress indicators help users by:

- Reducing uncertainty.
- Making long forms feel shorter.
- Showing how much work remains.
- Helping users estimate the time needed.
- Giving users confidence to continue.
- Improving form completion rates.

---

# Real-World Examples

Progress indicators are commonly used in:

- Account registration.
- Online checkout processes.
- Job applications.
- Surveys.
- Insurance forms.
- Government service portals.
- Multi-step setup wizards.

---

# Final Recommendation

These are just a few best practices to keep in mind when designing progress indicators for forms, registration, and setup processes.

Study how large websites implement progress indicators.

Pay attention to:

- Progress bars.
- Step numbers.
- Percentages.
- Section titles.
- Previous and Next navigation.
- Accessibility features.

After designing your own progress indicator, test it with real users to ensure it is easy to understand and provides a smooth experience.

---

# Summary

## Progress Indication

Progress indication helps users understand where they are in a multi-step process and how much remains before completion.

---

## Best Practices

- ✔ Keep the progress indicator simple.
- ✔ Allow users to return to previous steps.
- ✔ Make the progress indicator easy to find.
- ✔ Include clear section titles.
- ✔ Display step numbers.
- ✔ Show completion percentages.
- ✔ Use a visible progress bar.
- ✔ Support accessibility using ARIA attributes.
- ✔ Test your design with real users.

---

# Key Takeaway

A well-designed progress indicator makes long forms, registration processes, and setup wizards easier to complete by providing transparency, clear navigation, and helpful feedback throughout the entire process.
