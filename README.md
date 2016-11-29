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

