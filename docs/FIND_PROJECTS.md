## Find Your Projects 

In this module, we'll continue working on our selection tags. We'll create a function that will query through the ***Projects Collection*** and find the project based on the tags each   . 




**✅ Step-by-step directions**

1. add a function that will load data to the repeater. Pass an empty array of selected categories as a parameter.
```
function loadDataToRepeater(selectedCategories = []) {

}
```

2. Add a query of the Project collection using the ***collectionName*** variable and add a condition for checking if results can be shown.
```
function loadDataToRepeater(selectedCategories = []) {

	let dataQuery = wixData.query(collectionName)

	if (selectedCategories.length > 0) {
		dataQuery = dataQuery.hasAll(fieldToFilterByInCollection, selectedCategories)
	}
	
}
```

3. Call the ***dataQuery*** variable that is querying through the ***Projects Collection***. Use the .find() function to return an object that contains the query definition. Next, return a new promise that will populate the repeater.

```
function loadDataToRepeater(selectedCategories = []) {

	let dataQuery = wixData.query(collectionName)

	if (selectedCategories.length > 0) {
		dataQuery = dataQuery.hasAll(fieldToFilterByInCollection, selectedCategories)
	}
	
	dataQuery
		.find()
		.then(results => {
			const itemsReadyForRepeater = results.items
			$w('#listRepeater').data = itemsReadyForRepeater;
            })
```

4. Add a condition for showing/hiding the 'No Results' text.

```
dataQuery
		.find()
		.then(results => {
			const itemsReadyForRepeater = results.items
			$w('#listRepeater').data = itemsReadyForRepeater;

			const isRepeaterEmpty = itemsReadyForRepeater.length === 0

			if (isRepeaterEmpty) {
				$w('#noResultsFound').show()
			} else {
				$w('#noResultsFound').hide()
			}
		})
}
```
Nice! Now test it out, your projects should  filter based on the selected categories. 

⏩ Next Module => [Corvid + SendGrid ](PACKAGE_MANAGER.md)
