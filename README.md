#React Timeline

A vertical timeline component for React.js. View chronological events in a pleasant way. 


####Features
- Responsive & mobile-friendly
- Easily customized
- Gracefully handles overflow and non-uniform content
- Lightweight (only CSS and SVG)


####View Example 
http://aaron9000.github.io/react-timeline/

-


####Add to Existing Project
`npm install react-timeline --save`


####Usage
```js
import ReactDOM from 'react-dom';
import Timeline from 'react-timeline';
const events = require('events.json'); // See sample data below

ReactDOM.render(<Timeline events={events} />, document.getElementById('root'));
```

[Sample Data](https://gist.github.com/aaron9000/ca9600c9fc2e8c4b9a503b5789413852)


####Props
- `events`: **array** (required)
	- `date`: **date** (required)
	- `title`: **string** (required)
	- `imageUrl`: **string** (required)
	- `text`: **string** (required)
	- `onClick`: **function**
	- `buttonText`: **string**
	- `extras`: **object**
- `reverseOrder`: **boolean**
- `customStartLabel`: **component**
- `customEndLabel`: **component**
- `customHeader`: **component**
- `customImageBody`: **component**
- `customTextBody`: **component**
- `customFooter`: **component**

####Custom Event Data
To pass extra data into custom components, use the `extras` field on the `event` model.

####Custom Styles
To customize the timeline styles, add CSS to override [timeline.css](https://github.com/aaron9000/react-timeline/blob/master/lib/timeline.css). 

####Custom Dot Pattern
The dots are defined in CSS using a [base64-encoded image](https://www.base64-image.de/). Encode a new image and override the corresponding CSS class.

####Custom Components
For more advanced customization, you can pass in custom components to replace the defaults. Custom components will be passed an `event` model in props.
```js

// A custom header to replace the default
const CustomHeader = (props) => {

    // The corresponding "event" model
    const {title, extras} = props.event;
    
    // Custom data payload
    const {customField} = extras;

    // Use your own CSS
    return <div className="custom-header">
        <h1>{title}</h1>
        <p>{customField}</p>
    </div>;
};

ReactDOM.render(<Timeline events={events} customHeader={CustomHeader}/>, document.getElementById('root'));
```

####Run Example Project
```
npm install
npm run example
```
Then, visit [localhost:3000/example](http://localhost:3000/example) in your browser browser.

####Run Tests
```
npm run test
```

####Screenshot
![screenshot](https://github.com/aaron9000/react-timeline/blob/master/assets/screenshot.png)
