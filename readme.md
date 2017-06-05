# [WIP] Salt - Layout

> PostCSS plugin to add a collection of utilities related to the layout management for you CSS. This plugin is part of [Salt](https://github.com/alexandremasy/salt), a collection of tool to help you enforce a set of rule througout your application.



## Functionalities

1. **[Layout definition](#configuration)** Provide a way to declare the definition and relation of all the typographies used in an application.
   ​
2. **[Breakpoint](https://github.com/alexandremasy/postcss-salt-layout-breakpoint)** Generate the media queries.
   ​
3. **[Grid parser](https://github.com/alexandremasy/postcss-salt-layout-parser)** Walk through you css declarations to find the dynamic grid values and enforce a predefined one;
   ​



## Getting started

Installation is as easy as:

```shell
npm install --save postcss-salt-layout
```



**PostCSS**

Include the plugin in you build process:

```
@TODO
```



**Gulp**

Include the plugin in your build process:

```javascript
@TODO
```



This plugins depends on :

- [PostCSS](https://github.com/postcss/postcss)
- [Salt - Layout - Parser](https://github.com/alexandremasy/postcss-salt-layout-parser)
- [Salt - Layout - Breakpoint](https://github.com/alexandremasy/postcss-salt-layout-breakpoint)





## Configuration

### Syntax

The layout definition can be used by margin, padding, width, height, top, left, right, border properties. Here is the formal syntax:

```reStructuredText
{
  grid:         {
  	base:		<length>,
  	columns:	<int>,
  	gutter:		<length>,
  	sizes:		{
      [<scale>:	<length>]#
  	}
  },
  
  breakpoints:  {
    [<scale>:	<length>]#
  }
};
```



| Property                 | Type   | Description                              |
| ------------------------ | ------ | ---------------------------------------- |
| `grid` *optional*        | Object | A collection of all the options related to the grid. |
| `breakpoints` *optional* | Object | A collection of all the available breakpoints |



### Grid definition

| Property             | Type   | Description                              |
| -------------------- | ------ | ---------------------------------------- |
| `base` *optional*    | Length | The base used for all the grid computations. |
| `columns` *optional* | Array  | The number of columns in the grid.       |
| `gutter` *optional*  | Object | The width of the gutter relative to columns in the grid. |
| `sizes` *optional*   | Object | A map containing the grid size definition for each scale. More information in the [sizes definition](#sizes-definition) section. |



### Breakpoint definition

| Property | Description                              |
| -------- | ---------------------------------------- |
| `scale`  | The scale for which the breakpoint is declared. e.g. `xxs` |
| `length` | The breakpoint value                     |



## Example

```javascript
var layout = {
  grid: {
    base:		"16px",
    columns: 	12,
    gutter:	 	.5,
    sizes:{
      xxs:    	.25,
      xs:     	.5,
      s:      	.75,
      m:      	1,
      l:      	1.5,
      xl:     	2,
      xxl:    	4
    }
  )
  
  breakpoints: {
    xxs:    	"320px",
    xs:     	"375px",
    s:      	"425px",
    m:      	"768px",
    l:      	"1024px",
    xl:    		"1200px",
    xxl:    	"1440px"
  }
};
```

