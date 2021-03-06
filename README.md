[![Published on Vaadin Directory](https://img.shields.io/badge/Vaadin%20Directory-published-00b4f0.svg)](https://vaadin.com/directory/component/orgchart-add-on)
[![Stars on vaadin.com/directory](https://img.shields.io/vaadin-directory/star/orgchart-add-on.svg)](https://vaadin.com/directory/component/orgchart-add-on)
[![Build Status](https://jenkins.flowingcode.com/job/OrgChart-14-addon/badge/icon)](https://jenkins.flowingcode.com/job/OrgChart-14-addon/)

# OrgChart Add-On

OrgChart Add-On is a Vaadin 14+ NPM mode integration of the library [OrgChart](https://github.com/dabeng/OrgChart).

## Features

- Supported library features:
	- data, 
    - pan, 
    - zoom,
    - zoominLimit, 
    - zoomoutLimit, 
    - direction, 
    - verticalDepth, 
    - depth, 
    - toggleSiblingsResp, 
    - nodeTitle, 
    - nodeContent, 
	- nodeTemplate
    - exportButton, 
    - exportFilename, 
    - exportFileextension (png & pdf)
- Enable/disable expand/collapse feature
- Add a chart title
- Drag and Drop

## Online demo

Try the add-on demo at http://addonsv14.flowingcode.com/orgchart

## Download release

Official releases at Vaadin Directory https://vaadin.com/directory/component/orgchart-add-on

## Building and running demo

- git clone repository
- mvn clean install
- cd demo
- mvn jetty:run

To see the demo, navigate to http://localhost:8080/

## Release notes

### Version 2.0.0
- Initial Version. This version allows to visualize an organizational chart and exported as a png or a pdf file. 
### Version 2.0.1
- Drag and Drop Version. This version allows to Drag and Drop OrgChart nodes. 
### Version 2.0.2
- Add support for node styling (e.g. change node colors)
### Version 2.0.3
- Add support for [node templates](https://rawgit.com/dabeng/OrgChart/master/demo/custom-template.html)
- Fix options chartDepth and chartVerticalDepth
- Fix export support in IE
- Update OrgChart library to version [2.1.3](https://github.com/dabeng/OrgChart/releases/tag/v2.1.3)
- Update jackson-databind dependency because of security vulnerabilities [(#7)](https://github.com/FlowingCode/OrgChartAddon/issues/7)
### Version 2.0.4
- Add support for click events [(#4)](https://github.com/FlowingCode/OrgChartAddon/issues/4) and tooltips in orgchart nodes  [(#9)](https://github.com/FlowingCode/OrgChartAddon/issues/9)
### Version 4.0.0
- Initial release for Vaadin 14+ (npm mode) 

## Roadmap

This component is developed as a hobby with no public roadmap or any guarantees of upcoming releases. That said, the following features are planned for upcoming releases:

- Edition of the organization chart 

## Issue tracking

The issues for this add-on are tracked on its github.com page. All bug reports and feature requests are appreciated. 

## Contributions

Contributions are welcome, but there are no guarantees that they are accepted as such. Process for contributing is the following:

- Fork this project
- Create an issue to this project about the contribution (bug or feature) if there is no such issue about it already. Try to keep the scope minimal.
- Develop and test the fix or functionality carefully. Only include minimum amount of code needed to fix the issue.
- Refer to the fixed issue in commit
- Send a pull request for the original project
- Comment on the original issue that you have implemented a fix for it

## License & Author

Add-on is distributed under Apache License 2.0. For license terms, see LICENSE.txt.

OrgChart Add-On is written by Paola De Bartolo

# Developer Guide

## Getting started

Here is a simple example on how to try out the add-on component:

```java
  OrgChartItem item1 = new OrgChartItem(1, "Root item", "Root Level");
  OrgChartItem item2 = new OrgChartItem(2, "Item 2", "Level 1");
  OrgChartItem item3 = new OrgChartItem(3, "Item 3", "Level 1");        
  item1.setChildren(Arrays.asList(item2, item3));
  
  OrgChart orgChart = new OrgChart(item1);
  orgChart.setChartTitle("A Title");
  orgChart.setChartNodeContent("title");
  orgChart.setChartExportButton(true);
  orgChart.setZoom(true);
  orgChart.setChartDraggable(true);
  
  // add to a layout
  VerticalLayout layout = new VerticalLayout();
  layout.addComponent(orgChart);
```


