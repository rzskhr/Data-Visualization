Here are the steps you took to accomplish this in the JavaScript console while viewing a course viewer page in Chrome. Note that the quotes used in expressions are straight, plain quotes (text-only) not curly, smart quotes (rich text format).

1. Paste contents of d3.min.js file into console.
2. File can be found [here](https://d3js.org/d3.v3.min.js).
3. Expected Output: ```True```
4. Clear content from div in course viewer:
```javascript
Input: d3.select('.main').html('');
```
5. Expected Output: ```>[Array[1]]```
6. Define svg variable:
Input:
```javascript
var svg = d3.select('.main').append('svg')
```
7. Expected Output: ```undefined```
8. Assign y axis linear scale to y variable. This axis describes life expectancy. Note that while the height of the svg is 300 pixels, only 250 are used for the y axis to leave a buffer. Also, for the y axis the max value comes first because of a quirk with how objects are drawn in the browser: highest value at bottom of axis.
Input:
```javascript
var y = d3.scale.linear().domain([15,90]).range([250,0]);
```
9. Expected Output: ```undefined```
10. Assign X axis scale to x variable. This axis describes annual income.
Input:
```javascript
var x = d3.scale.log().domain([250,100000]).range([0,600]);
```
11. Expected Output: ```undefined```
12. Assign radius scale to r variable. The radius corresponds to the square root of the population.
Input:
```javascript
var r = d3.scale.sqrt().domain([52070, 1380000000]).range([10, 50]);
```
13. Check scaling with console.log by plugging in life expectancy for China in y variable, and annual income per person for China in x variable, and population for China in r variable.
Input:
```javascript
console.log(y(77), x(13330), r(1380000000));
```
14. Expected Output appox: 43.33333333333314 398.1976156961321 50
15. Append circle with attribute values for radius, fill color, center x and center y of circle:
Input:
```javascript
svg.append('circle').attr('r', r(1380000000)).attr('fill','red').attr('cx', x(13330)).attr('cy', y(77));
```
16. Expected Output: ```>[Array[1]]```
17. Look at placement of the circle in the svg, and compare with the placement in the original Gapminder World graph: https://www.gapminder.org/tools/#_chart-type=bubbles
