Use the useState() hook to create a state variable for the load status of the script.
Use the useEffect() hook to handle all the logic for loading and unloading the script anytime the src changes.
If no src value is present, set the status to 'idle' and return.
Use Document.querySelector() to check if a <script> element with the appropriate src value exists.
If no relevant element exists, use Document.createElement() to create one and give it the appropriate attributes.
Use the data-status attribute as a way to indicate the status of the script, setting it to 'loading' initially.
If a relevant element exists, skip initialization and update the status from its data-status attribute. This ensures that no duplicate element will be created.
Use EventTarget.addEventListener() to listen for 'load' and 'error' events and handle them by updating the data-status attribute and the status state variable.
Finally, when the component unmounts, use Document.removeEventListener() to remove any listeners bound to the element.
