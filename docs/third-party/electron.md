---
title: Electron
page_title: Electron | Kendo UI Third-Party Tools
description: "Learn how to use the Kendo UI widgets in an Electron application."
slug: electron_integration_kendoui
position: 12
---

# Electron

[Electron](https://electronjs.org/) is a framework for creating native desktop applications with web technologies like JavaScript, HTML, and CSS.

## Adding CSS and JavaScript References

To use Kendo UI in your Electron projects, include the required JavaScript and CSS files.

### Using Local Files

Due to the Node.js integration of Electron, some extra symbols were inserted into the DOM&mdash;`module`, `exports`, and `require`. To include the scripts, use the `require` symbol.

##### Example

    <link href="lib/css/kendo.common.min.css" rel="stylesheet">
    <link href="lib/css/kendo.rtl.min.css" rel="stylesheet">
    <link href="lib/css/kendo.default.min.css" rel="stylesheet">
    <link href="lib/css/kendo.mobile.all.min.css" rel="stylesheet">

    <script>window.$ = window.jQuery = require('./lib/js/jquery.min.js');</script>
    <script>require('./lib/js/kendo.all.min.js')</script>

### Using CDN Services

Before you include the jQuery library, unset `module`.

##### Example

    <link rel="stylesheet" href="https://kendo.cdn.telerik.com/{{ site.cdnVersion }}/styles/kendo.common.min.css">
    <link rel="stylesheet" href="https://kendo.cdn.telerik.com/{{ site.cdnVersion }}/styles/kendo.rtl.min.css">
    <link rel="stylesheet" href="https://kendo.cdn.telerik.com/{{ site.cdnVersion }}/styles/kendo.default.min.css">
    <link rel="stylesheet" href="https://kendo.cdn.telerik.com/{{ site.cdnVersion }}/styles/kendo.mobile.all.min.css">

    <script>if (typeof module === 'object') {window.module = module; module = undefined;}</script>
    <script src="https://code.jquery.com/jquery-1.12.3.min.js"></script>
    <script src="https://kendo.cdn.telerik.com/{{ site.cdnVersion }}/js/kendo.all.min.js"></script></head>
    <script>if (window.module) module = window.module;</script>

## Basic Usage

The following example assumes that the Kendo UI scripts and stylesheets were added to the document.

##### Example

    <div id="grid"></div>
    <script>
    $("#grid").kendoGrid({
        columns: [
            { field: "name" },
            { field: "age" }
        ],
        dataSource: {
            data: [
                { name: "Jane Doe", age: 30 },
                { name: "John Doe", age: 33 }
            ]
        }
    });
    </script>

## Application Distribution

To distribute your app with Electron, follow the steps outlined in the [Application Distribution](https://electronjs.org/docs/tutorial/application-distribution) Electron documentation article.

Alternatively, you can use a third party packaging tool:

* [electron-forge](https://github.com/electron-userland/electron-forge)
* [electron-builder](https://github.com/electron-userland/electron-builder)
* [electron-packager](https://github.com/electron-userland/electron-packager)

## Sample Application

The sample app is aimed at executives, analysts, or sales representatives. It helps them establish targets based on insights into historical data as well as track sales and product performance in real time. It showcases some of the most popular Kendo UI widgets, such as Scheduler, Grid, TabStrip, Charts and Map in a real world scenario. It has a simple and responsive UI based on Bootstrap and works on a wide range of devices.

<a href="https://github.com/telerik/kendo-electron-dashboard" target="_blank"><img src="/images/northwind.png"></a>

## See Also

* [Electron Documentation](https://electronjs.org/docs)
* [Electron FAQ](https://electronjs.org/docs/faq)