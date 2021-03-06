# polymer-pie-chart

**This element is compatible with Polymer 0.5.**

__Example:__

```
	<polymer-element name="polymer-pie-chart-demo">
		<template>
			<style>
				#container {
					width: 800px;
					margin: 0 auto;
					text-align: center;
				}
			</style>
			<div id="container">
				<p>An example of using <code>&lt;polymer-pie-chart&gt;</code>:</p>
				<polymer-pie-chart
					title="Demo Pie Chart"
					toolTipLabel="Demo Label"
					defaultColor="#ccc"
					data="{{ data }}">
					</polymer-pie-chart>
			</div>
		</template>
		<script src="../lodash/lodash.js"></script>
		<script>
			function randomValue() {
				return Math.floor(Math.random()*800) + 300;
			}
			Polymer({
				publish: {
				},
				ready: function() {
					var poly = this;
					poly.data = [
						['Category Default', randomValue()],
						['Category Red', randomValue(), '#c66'],
						['Category Green', randomValue(), '#6c6'],
						['Category Blue', randomValue(), '#66c'],
					];
					setInterval(function() {
						var data = _.clone(poly.data);
						_.each(data, function(slice) {
							slice[1] = randomValue();
						});
						poly.data = data;
					}, 3500);
				}
			});
		</script>
	</polymer-element></polymer-element>
	<polymer-pie-chart-demo></polymer-pie-chart-demo>
```
# Attributes

#### `coordinates`

An array of arrays of x and y values. y values must be numbers.

#### `title`

Title displayed above graph;

#### `yAxisTitle`

Title displayed left of graph to indicate y values;