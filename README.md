# encyclopedia.Modern_Developer

#1.  `<col />` #

The `<col>` tag is a block element that is used in html tables to specify column properties for columns within a `<colgroup>` tag. It does not require a closing tag. Instead of styling `<td>`s individually, they can be placed within a `<colgroup>` and `<col>` tags used to style them. The `span` attribute of a `<col>` tag can be used to specify how many `<td>`'s within a row the `<col>`'s style should be applied.

Example :

	<!DOCTYPE html>
	<html>
	<head>
     	<title>JS Bin</title>
	</head>
    <body>
	    <table border="1">
		    <colgroup>
		      <col style="background:blue;">
		      <col span="3" style="background:pink;">
		      <col style="background:orange;">
		    </colgroup>
		    <tr>
		      <td>One</td>
		      <td>Two</td>
		      <td>Three</td>
		      <td>Four</td>
		      <td>Five</td>
		    </tr>
		    <tr>
		      <td>One</td>
		      <td>Two</td>
		      <td>Three</td>
		      <td>Four</td>
		      <td>Five</td>
		    </tr>
	    </table>
    </body>
    </html>
	

In the example above all `<td>`'s in column one will be blue due to the `<col>` tag setting the background color. Columns 2-4 will be pink as the `<span>` attribute is used to specify that the styling is to be applied to 3 columns.


----------

#2.  `<td>` #

The `<td>` element is used in html tables to create a single cell in row. `<td>`'s are inline elements and must be children of `<tr>` (row) elements. They require both open and closing tags, between which the cell's content is placed. `<tr>` (rows) can contain many `<td>` elements. Each row must have an equal number of `<td></td>` pairs in order for the rows to be of equal size, unless the `colspan` attribute is used. This allows `<td>`'s to which they are applied to span across more than one cell.

Example :

    <table>
		<thead></thead>
		<tbody>
			<tr>
				<td>One</td><td>Two</td><td>Three</td>
			</tr>
			<tr>
				<td>One</td><td>Two</td><td>Three</td>
			</tr>
			<tr>
				<td>One</td><td colspan=2>Two</td>
			</tr>
		</tbody>
	</table>

In the example above the first and second rows have 3 cells each. The third row has only 2 cells but setting the `colspan` attribute to 2 allows the second cell to span across 2 of the cells above, keeping the columns uniform.


----------

#3.  z-index #

The z-index is used to describe a html elements position or hierarchy along the Z axis which runs perpendicular to the viewport. In other words this describes the order in which elements will appear when placed directly upon each other.

There are a number of things that affect the order in which elements are ordered along the Z axis. In order to describe how z-indices work a definition of stacking contexts is necessary. Stacking contexts are elements that contain a group of layers each stacked upon one another from bottom up.The order of each layer is determined according to certain rules which are dependent on properties of each layer. 

Applying z-indices can change the natural order in which each layer is stacked. z-indices can only be applied to elements that have position set to relative, absolute or fixed.  z-indices take a positive or negative integer value. Elements with a greater value are stacked over elements with lower values. A z-index value of auto will make an element have the same order as its parent.

CSS : styles.css

    img {
    	position: absolute;
    	left: 0px;
    	top: 0px;
    	z-index: 0;
    }

	.dummy-text{
		position: absolute;
    	left: 0px;
    	top: 0px;
    	z-index: 1;
	}

Html:

    <!DOCTYPE html>
	<html>
		<head>
			<link rel="stylesheet" href="styles.css">
		</head>
		<body>
			<img src="testImage.png" width="100" height="100>
			<p class="dummy-text">
				This text will appear over the image.
			</p>
		</body>


In the example above the text will appear on top of the image due to it having a greater z-index value.


----------

#4.  table-layout #

The table-layout property sets the table layout algorithm to be used for a table. table-layout supports auto, fixed, initial, and inherit.

The default property value `auto` automatically sets the table layout algorithm to the widest column width is set by the content in the cells making it an unbreakable by containing all content within the table cell. The one drawback is that it can be slow because it needs to read through all the content cells in the table before it can determine the final layout width.

The `fixed` property value is dependent on the table's width and the width of the columns, not the contents of the cells. This horizontal layout is faster because it allows the browser to display the table once the first row has been received.

The last two properties are `initial` and `inherit`. The `initial` property simply sets its default value while `inherit` inherits its property from its parent element.


```
table.ex1 {
    table-layout: auto;
}

table.ex2 {
    table-layout: fixed;
}

<table class="ex1">
  <tr>
    <td width="5%">1000000000000000000000000000</td>
    <td width="95%">10000000</td>
  </tr>
</table>

<p>table-layout: fixed:</p>
<table class="ex2">
  <tr>
    <td width="5%">1000000000000000000000000000</td>
    <td width="95%">10000000</td>
  </tr>
</table>
```
In the examples above we have set the the first example to `auto`. This will make sure both numbers will fit within the cell. The second example will cause the larger number to overflow outside the containing cell.


----------

#5.  parseFloat() #

The `parseFloat()` function parses a string argument passed into it and returns a floating point number. `NaN` is returned if the string does not begin with a valid number. `parseFloat()` parses and returns the first number that it encounters in the string. Additionally parsing will stop immediately and the value is returned when `parseFloat()` encounters a character that is not a valid number.

Below are parsed string examples.

```
parseFloat("20"); // -> 20
parseFloat("20.00"); // -> 20
parseFloat("4.20"); // -> 4.20
parseFloat("100 200 300"); // -> 100
parseFloat("802 Vermont"); // -> 802
parseFloat("Vermont 802"); // -> NaN

```

----------

#6.  String.prototype.valueOf() #

This method is usually called internally by JavaScript and not explicitly in code.

The `valueOf()` function is a internal method of JavaScript’s built in String object. It returns a primitive value String object as a string data type. The value returned is the same as you would get using `String.prototype.toString()`. `valueOf()` is usually never explicitly used in code. The following is an example of `valueOf()`:

```
var str = new String('Hello world');
str.valueOf(); // -> 'Hello world'
```

