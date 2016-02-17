# d3-square-tile-map
A map of the United States where each state is an equal sized square.

### Rendering the Map
Create the element that will contain your map.
```html
<div class="map-container"></div>
```
Call `d3.squareMap.render()` on your container element. `render()` takes two arguments: the path to your CSV data set and your container element.
```javascript
d3.squareMap.render('states.csv', '.map-container');
```
Be sure to render your map only *after* you have modified its properties.

The CSV file should have two columns: `state` and `data`. Format as follows:

```javascript
state,data
AL,12.5
AK,14
AR,22
CA,9
```

By default, the map will render at 100% width of the container element. See the **changing properties** section to learn how to change that.

### Changing Properties
To change properties of the map, use the `setAttr()` method. This method takes an object of the properties you wish to change as its argument. Be sure to call the `render()` method only after modifying properties.
```javascript
d3.squareMap.setAttr({
    colorSet: 'Greens',
    labelStyle: 'full'
}).render('.map-container');
```
The following table contains a list of all modifiable properties.

|Property     |Description       |Values       |Default        |
|-------------|------------------|-------------|---------------|
|`width`      |Width of the map. When it is set to `null`, the map fills the width of its containing element.|Any number or `null`|`null`|
|`colorSet`   |The ColorBrewer palette used for the map. |A string with the name of a ColorBrewer palette. Reference is [here](https://bl.ocks.org/mbostock/5577023).|`'Blues'`|
|`colorNumber`|Number of steps in ColorBrewer palette. |An integer between 3 and whatever the maximum of your chosen palette is. Usually between 9 and 12.|`6`|
|`labels`     |Whether the map has labels on each state.|`true` or `false`|`true`|
|`labelTypeface`|Font family of the state labels.|Any font family.|`sans-serif`|
|`labelStyle`|The kind of labels used.|`abbr` (postal abbreviations e.g. CT, NY, CA)<br>`ap` (AP style e.g. Conn., N.Y., Calif.)|`ap`|
|`labelColor`|Color of the state labels.|Any color|`'white'`|
