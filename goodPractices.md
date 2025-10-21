# Good Practices


### Initializing objects
If you're getting data with option keys from the backend and that data needs to be transformed in the frontend, don't initialize empty keys
❌
```javascript
const dataFromApi = {"name": "John", "optionalKey": "may or may not be"};
const transformedData = (dataFromApi) => {
	return {
		data: dataFromApi.name,
		optionalKey:dataFromApi.optionalKey
	};
};
```
✅
```javascript
const dataFromApi = {"name": "John", "optionalKey": "may or may not be"};
const transformedData = (dataFromApi) => {
	let data = {};
	if(dataFromApi.name) data.name = dataFromApi.name;
	if(dataFromApi.optionalKey) = dataFromApi.optionalKey;
	return data;
};
```
