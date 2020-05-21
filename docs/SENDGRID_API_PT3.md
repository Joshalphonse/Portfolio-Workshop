## Wix Fetch + Sengrid PT 3! 
1. Go to your Contact page and open the IDE. Import the **sendEmail** and **sendEmailWithRecipient** functions from the **email.js** file. 

```
import { sendEmail, sendEmailWithRecipient } from 'backend/email'


```
2. Add a function called sendFormData. Create variables for the values of each text input.
```
import { sendEmail, sendEmailWithRecipient } from 'backend/email'

$w.onReady(function () {

});

function sendFormData() {
	const subject = `New Submission from ${$w("#nameInput").value}`;
	const body = `First Name: ${$w("#nameInput").value}
	\rEmail: ${$w("#emailInput").value}
    \Message: ${$w("#messageInput").value}`;
	const recipient = $w("#emailInput").value;
}
```
3. Call the the functions you imported from the backend and use the new variables to populate the needed parameters. 
```
import { sendEmail, sendEmailWithRecipient } from 'backend/email'

$w.onReady(function () {
	

});

function sendFormData() {
	const subject = `New Submission from ${$w("#nameInput").value}`;
	const body = `First Name: ${$w("#nameInput").value}
	\rEmail: ${$w("#emailInput").value}
    \Message: ${$w("#messageInput").value}`;
	const recipient = $w("#emailInput").value;

	sendEmailWithRecipient(subject, body, recipient)
		.then(response => console.log(response));

	sendEmail(subject, body)
		.then(response => console.log(response));
}
```
4. In the **$w.onReady()** function use **$w()** to select the dataset created for the contact form collection. Use the [**onAfterSave()** ](https://www.wix.com/corvid/reference/wix-dataset.Dataset.html#onAfterSave)function with the sendFormData function as an argument. Also you can also add placeholders!   
```
import { sendEmail, sendEmailWithRecipient } from 'backend/email'

$w.onReady(function () {
	$w("#dataset1").onAfterSave(sendFormData);
	// placeholders
	$w("#nameInput").placeholder = "First Name";
	$w("#emailInput").placeholder = "Email";
	$w("#messageInput").placeholder = "Send a message!";

});

function sendFormData() {
	const subject = `New Submission from ${$w("#nameInput").value}`;
	const body = `First Name: ${$w("#nameInput").value}
	\rEmail: ${$w("#emailInput").value}
    \Message: ${$w("#messageInput").value}`;
	const recipient = $w("#emailInput").value;

	sendEmailWithRecipient(subject, body, recipient)
		.then(response => console.log(response));

	sendEmail(subject, body)
		.then(response => console.log(response));
}
```

❗ Go to preview, play with your new contact form!
⏩ Next Module => [Flare up your portfolio with the Timeline API!](TIMELINE_API.md)