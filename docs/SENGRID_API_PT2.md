## Wix Fetch + Sengrid PT 2! 

1. Add a new jws file called **email.jsw** by clicking **New Web Module** in the Site Structure panel.

   <p padding="40px"><img src="assets/add-jsw.png" alt="Add JSW" width="40%" height="40%"></p>

2. Remove the template code and import the **sendWithService** function from **sendGrid.jsw**
```
import {sendWithService} from 'backend/sendGrid';

}
```

3. export a new function called **sendEmail**.
```
import {sendWithService} from 'backend/sendGrid';

export  function sendEmail(subject, body) {
  const key = <YOUR API KEY>
  const sender = "joshuaa@wix.com";
  const recipient = "joshuaa@wix.com";
  return sendWithService(key, sender, recipient, subject, body);
}
```


4. Add another function to send an email to the user that is filling the
```
import {sendWithService} from 'backend/sendGrid';

export  function sendEmail(subject, body) {
  const key ='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';
  const sender = "joshuaa@wix.com";
  const recipient = "joshuaa@wix.com";
  return sendWithService(key, sender, recipient, subject, body);
}

export  function sendEmailWithRecipient(subject, body, recipient) {
  const key = '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';
  const sender = "joshuaa@wix.com";
  return sendWithService(key, sender, recipient, subject, body);
}

```
******
## FRONT END



5. On the Contact page add a [dataset](https://www.wix.com/corvid/reference/wix-dataset.html) by clicking the <img src="assets/element-add.png" alt="Element Add" width="3%" height="3%"> from the vertical menu on the left side of the page. Then click **Database** >> **Dataset**. <p padding="40px"><img src="assets/add-dataset.png" alt="Add dataset" width="40%" height="40%"></p>
6. Click <img src="assets/dataset-settings-btn.png" alt="Dataset Settings Button" width="8%" height="8%"> to access the Dataset Settings.
7. Set the collection to **Contact Form**. <br>Set the mode to **Write-Only**. <p padding="40px"><img src="assets/data-set-settings2.png" alt="Add dataset" width="30%" height="30%"></p>
8. Connect the input boxes to the dataset by clicking the Connect Button <img src="assets/connect-btn.png" alt="Connect Button" width="3%" height="3%">. Then connect the Button and select **Submit** under the 'Click action connects to' dropdown <p padding="40px"><img src="assets/connect-collection.png" alt="Repeater Connect Panel" width="40%" height="40%"></p>

Hooray! Now let's continue to the next stage: Sendgrid Front end! 



⏩ Next Module => [Sendgrid Part 3](SENDGRID_API_PT3.md)
