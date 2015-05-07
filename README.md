# polymer-pie-chart

**This element is compatible with Polymer 0.5.**

__Example:__

```
	<polymer-element name="polymer-histogram-demo">
		<template>
			<style>
				#container {
					width: 800px;
					margin: 0 auto;
					text-align: center;
				}
			</style>
			<div id="container">
				<p>An example of using <code>&lt;polymer-histogram&gt;</code>:</p>
				<polymer-histogram
					coordinates="{{ coordinates }}"
					title="Demo Graph"
					yAxisTitle="Y Axis Label"></polymer-histogram>
			</div>
		</template>
		<script src="../lodash/lodash.js"></script>
		<script>
			function setFake() {
				return [Math.floor(Math.random()*10), Number((Math.random() * 10).toFixed(2)) ];
			}
			Polymer({
				publish: {
					coordinates: [
						setFake(),
						setFake(),
						setFake(),
						setFake(),
						setFake()
					]
				},
				ready: function() {
					var poly = this;
					setInterval(function() {
						var coordinates = _.clone(poly.coordinates);
						coordinates = coordinates.slice(1);
						coordinates.push(setFake());
						poly.coordinates = coordinates;
					}, 5000);
				}
			});
		</script>
	</polymer-element></polymer-element>
	<polymer-histogram-demo></polymer-histogram-demo>
```
# Attributes

#### `coordinates`

An array of arrays of x and y values. y values must be numbers.

#### `title`

Title displayed above graph;

#### `yAxisTitle`

Title displayed left of graph to indicate y values;