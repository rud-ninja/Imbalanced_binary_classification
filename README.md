# Imbalanced_binary_classification

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>insurance_prediction2</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
/*!

Copyright 2015-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-top:0;
  margin-bottom:10px; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  line-height:40px;
  font-size:36px; }

h2.bp3-heading, .bp3-running-text h2{
  line-height:32px;
  font-size:28px; }

h3.bp3-heading, .bp3-running-text h3{
  line-height:25px;
  font-size:22px; }

h4.bp3-heading, .bp3-running-text h4{
  line-height:21px;
  font-size:18px; }

h5.bp3-heading, .bp3-running-text h5{
  line-height:19px;
  font-size:16px; }

h6.bp3-heading, .bp3-running-text h6{
  line-height:16px;
  font-size:14px; }
.bp3-ui-text{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400; }

.bp3-monospace-text{
  text-transform:none;
  font-family:monospace; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  line-height:1.5;
  font-size:14px; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    margin:20px 0;
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15); }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  text-decoration:none;
  color:#106ba3; }
  a:hover{
    cursor:pointer;
    text-decoration:underline;
    color:#106ba3; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  text-transform:none;
  font-family:monospace;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  background:rgba(255, 255, 255, 0.7);
  padding:2px 5px;
  color:#5c7080;
  font-size:smaller; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  text-transform:none;
  font-family:monospace;
  display:block;
  margin:10px 0;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  background:rgba(255, 255, 255, 0.7);
  padding:13px 15px 12px;
  line-height:1.4;
  color:#182026;
  font-size:13px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    padding:0;
    color:inherit;
    font-size:inherit; }

.bp3-running-text kbd, .bp3-key{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  min-width:24px;
  height:24px;
  padding:3px 6px;
  vertical-align:middle;
  line-height:24px;
  color:#5c7080;
  font-family:inherit;
  font-size:12px; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    background:#394b59;
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  margin:0 0 10px;
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  margin:0;
  padding:0;
  list-style:none; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    margin-top:0;
    margin-right:20px;
    font-size:40px; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  margin:0;
  cursor:default;
  height:30px;
  padding:0;
  list-style:none; }
  .bp3-breadcrumbs > li{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }
    .bp3-breadcrumbs > li::after{
      display:block;
      margin:0 5px;
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 0 0-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 0 0 1.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      width:16px;
      height:16px;
      content:""; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    vertical-align:baseline;
    font-size:inherit;
    font-weight:inherit; }

.bp3-breadcrumbs-collapsed{
  margin-right:2px;
  border:none;
  border-radius:3px;
  background:#ced9e0;
  cursor:pointer;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    display:block;
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    width:16px;
    height:16px;
    content:""; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    text-decoration:none;
    color:#182026; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  min-width:30px;
  min-height:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#106ba3; }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0e5a8a;
      background-image:none; }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#0d8050; }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0a6640;
      background-image:none; }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#bf7326; }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a66321;
      background-image:none; }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#c23030; }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a82a2a;
      background-image:none; }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-width:40px;
    min-height:40px;
    padding:5px 15px;
    font-size:16px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      position:absolute;
      margin:0; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-image:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button.bp3-minimal:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:-1px;
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-button-group.bp3-minimal .bp3-button{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      width:unset;
      height:100%; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  line-height:1.5;
  font-size:14px;
  position:relative;
  border-radius:3px;
  background-color:rgba(138, 155, 168, 0.15);
  width:100%;
  padding:10px 12px 9px; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout .bp3-heading{
    margin-top:0;
    margin-bottom:5px;
    line-height:20px; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  background-color:#ffffff;
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
    background-color:#30404d; }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  opacity:0.9;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  margin:5px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }

.bp3-dialog{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ebf1f5;
  width:500px;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#293742;
    color:#f5f8fa; }

.bp3-dialog-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  background:#ffffff;
  min-height:40px;
  padding-right:5px;
  padding-left:20px; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
    background:#30404d; }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  margin:20px;
  line-height:18px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-drawer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    top:0;
    right:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-bottom{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-left{
    top:0;
    bottom:0;
    left:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-right{
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#30404d;
    color:#f5f8fa; }

.bp3-drawer-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  min-height:40px;
  padding:5px;
  padding-left:20px; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  overflow:auto;
  line-height:18px; }

.bp3-drawer-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  padding:10px 20px; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  display:inline-block;
  position:relative;
  cursor:text;
  max-width:100%;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    position:absolute;
    top:-3px;
    right:-3px;
    bottom:-3px;
    left:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  display:inherit;
  position:relative;
  min-width:inherit;
  max-width:inherit;
  vertical-align:top;
  text-transform:inherit;
  letter-spacing:inherit;
  color:inherit;
  font:inherit;
  resize:none; }

.bp3-editable-text-input{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  width:100%;
  padding:0;
  white-space:pre-wrap; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    position:absolute;
    left:0;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    z-index:2;
    border-radius:inherit; }
    .bp3-control-group .bp3-input:focus{
      z-index:14;
      border-radius:3px; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    z-index:4;
    border-radius:inherit; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:-1px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    margin-right:0;
    border-radius:0 3px 3px 0; }
  .bp3-control-group > :only-child{
    margin-right:0;
    border-radius:3px; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      margin-top:0;
      border-radius:3px 3px 0 0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  display:block;
  position:relative;
  margin-bottom:10px;
  cursor:pointer;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    position:absolute;
    top:0;
    left:0;
    opacity:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    display:inline-block;
    position:relative;
    margin-top:-3px;
    margin-right:10px;
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    cursor:pointer;
    width:1em;
    height:1em;
    vertical-align:middle;
    font-size:16px;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none; }
    .bp3-control .bp3-control-indicator::before{
      display:block;
      width:1em;
      height:1em;
      content:""; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#d8e1e8; }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-top:1px;
    margin-left:10px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 0 0-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0 0 12 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    width:auto;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      position:absolute;
      left:0;
      margin:2px;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      background:#ffffff;
      width:calc(1em - 4px);
      height:calc(1em - 4px);
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background:#394b59; }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    text-align:center;
    font-size:0.7em; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    visibility:hidden;
    margin-right:1.2em;
    margin-left:0.5em;
    line-height:0; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    visibility:visible;
    margin-right:0.5em;
    margin-left:1.2em;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    visibility:visible;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    visibility:hidden;
    line-height:0; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0)); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background:#202b33; }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  display:inline-block;
  position:relative;
  cursor:pointer;
  height:30px; }
  .bp3-file-input input{
    opacity:0;
    margin:0;
    min-width:200px; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(206, 217, 224, 0.5);
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6);
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        outline:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        cursor:not-allowed;
        color:rgba(92, 112, 128, 0.6); }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:rgba(57, 75, 89, 0.5);
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          -webkit-box-shadow:none;
                  box-shadow:none;
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  position:absolute;
  top:0;
  right:0;
  left:0;
  padding-right:80px;
  color:rgba(92, 112, 128, 0.6);
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-file-upload-input::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026;
    min-width:24px;
    min-height:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    position:absolute;
    top:0;
    right:0;
    margin:3px;
    border-radius:3px;
    width:70px;
    text-align:center;
    line-height:24px;
    content:"Browse"; }
    .bp3-file-upload-input::after:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-file-upload-input:active::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-large .bp3-file-upload-input{
    height:40px;
    line-height:40px;
    font-size:16px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-width:30px;
      min-height:30px;
      margin:5px;
      width:85px;
      line-height:30px; }
  .bp3-dark .bp3-file-upload-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
        background-color:#30404d; }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
        background-color:#202b33;
        background-image:none; }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-file-upload-input:active::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }

.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    margin-top:5px;
    color:#5c7080;
    font-size:12px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      margin:0 10px 0 0;
      line-height:40px; }
    .bp3-form-group.bp3-inline label.bp3-label{
      margin:0 10px 0 0;
      line-height:30px; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-width:24px;
    min-height:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-icon{
    z-index:1;
    color:#5c7080; }
    .bp3-input-group > .bp3-icon:empty{
      line-height:1;
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-width:30px;
    min-height:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none; }
  .bp3-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-input.bp3-large{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-top:0;
  margin-bottom:15px; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    width:100%;
    vertical-align:top;
    font-weight:400; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  width:30px;
  min-height:0;
  padding:0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  border-radius:3px;
  width:100%;
  height:30px;
  padding:0 25px 0 10px;
  -moz-appearance:none;
  -webkit-appearance:none; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(167, 182, 194, 0.3);
    text-decoration:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(115, 134, 148, 0.3);
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  height:40px;
  padding-right:35px;
  font-size:16px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#202b33;
    background-image:none; }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:rgba(206, 217, 224, 0.5);
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  position:absolute;
  top:7px;
  right:7px;
  color:#5c7080;
  pointer-events:none; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  position:relative;
  vertical-align:middle;
  letter-spacing:normal; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    top:12px;
    right:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    vertical-align:top;
    text-align:left; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-top:6px;
  padding-bottom:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(92, 112, 128, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
    -webkit-box-shadow:none;
            box-shadow:none; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(92, 112, 128, 0.3);
  cursor:pointer; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  top:40px;
  padding-bottom:0; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-right:0;
  margin-left:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  line-height:1;
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  line-height:1;
  font-family:"Icons20";
  font-size:inherit;
  font-weight:400;
  font-style:normal; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  margin:0;
  border-radius:3px;
  background:#ffffff;
  min-width:180px;
  padding:5px;
  list-style:none;
  text-align:left;
  color:#182026; }

.bp3-menu-divider{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  padding:5px 7px;
  text-decoration:none;
  line-height:20px;
  color:inherit;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    margin-top:2px;
    color:#5c7080; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    outline:none !important;
    background-color:inherit !important;
    cursor:not-allowed !important;
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    padding:9px 7px;
    line-height:22px;
    font-size:16px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-top:1px;
      margin-right:10px; }

button.bp3-menu-item{
  border:none;
  background:none;
  width:100%;
  text-align:left; }
.bp3-menu-header{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    margin:0;
    padding:10px 7px 0 1px;
    line-height:17px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    padding-top:15px;
    padding-bottom:5px;
    font-size:18px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item.bp3-intent-primary{
  color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
    color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
    background-color:#137cbd; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
    background-color:#106ba3; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-success{
  color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
    color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
    background-color:#0f9960; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:active{
    background-color:#0d8050; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-warning{
  color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
    color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
    background-color:#d9822b; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
    background-color:#bf7326; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-danger{
  color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
    color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
    background-color:#db3737; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
    background-color:#c23030; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item::before,
.bp3-dark .bp3-menu-item > .bp3-icon{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item .bp3-menu-item-label{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
  background-color:rgba(138, 155, 168, 0.3); }

.bp3-dark .bp3-menu-item.bp3-disabled{
  color:rgba(167, 182, 194, 0.6) !important; }
  .bp3-dark .bp3-menu-item.bp3-disabled::before,
  .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
  .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
    color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  position:relative;
  z-index:10;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:100%;
  height:50px;
  padding:0 15px; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    position:fixed;
    top:0;
    right:0;
    left:0; }

.bp3-navbar-heading{
  margin-right:15px;
  font-size:16px; }

.bp3-navbar-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  margin:0 10px;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  height:100%;
  text-align:center; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  position:static;
  top:0;
  right:0;
  bottom:0;
  left:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    position:fixed;
    overflow:hidden; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    position:fixed;
    overflow:auto; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;
  opacity:1;
  z-index:20;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  position:relative;
  overflow:hidden; }

.bp3-panel-stack-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  z-index:1;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  height:30px; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  position:absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  background-color:#ffffff;
  overflow-y:auto; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  display:inline-block;
  z-index:20;
  border-radius:3px; }
  .bp3-popover .bp3-popover-arrow{
    position:absolute;
    width:30px;
    height:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      margin:5px;
      width:20px;
      height:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-top:-17px;
    margin-bottom:17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-right:17px;
    margin-left:-17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover .bp3-popover-content{
    position:relative;
    border-radius:3px; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg);
  border-radius:2px;
  content:""; }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  position:absolute;
  top:0;
  right:0;
  left:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  display:block;
  position:relative;
  border-radius:40px;
  background:rgba(92, 112, 128, 0.2);
  width:100%;
  height:8px;
  overflow:hidden; }
  .bp3-progress-bar .bp3-progress-meter{
    position:absolute;
    border-radius:40px;
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    width:100%;
    height:100%;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  cursor:default;
  color:transparent !important;
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  width:100%;
  min-width:150px;
  height:40px;
  position:relative;
  outline:none;
  cursor:default;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    opacity:0.5;
    cursor:not-allowed; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  top:5px;
  right:0;
  left:0;
  height:6px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  position:absolute;
  top:0;
  left:0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  width:16px;
  height:16px; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5;
    z-index:2;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab; }
  .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#bfccd6;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#5c7080; }
  .bp3-slider-handle .bp3-slider-label{
    margin-left:8px;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    background:#394b59;
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      background:#e1e8ed;
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    margin-left:8px;
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  position:absolute;
  padding:2px 5px;
  vertical-align:top;
  line-height:1;
  font-size:12px; }

.bp3-slider.bp3-vertical{
  width:40px;
  min-width:40px;
  height:150px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:0;
    bottom:0;
    left:5px;
    width:6px;
    height:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-top:-8px;
      margin-left:0; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      margin-left:0;
      width:16px;
      height:8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-top-left-radius:0;
      border-bottom-right-radius:3px; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      margin-bottom:8px;
      border-top-left-radius:3px;
      border-bottom-left-radius:0;
      border-bottom-right-radius:0; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round; }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      width:100%;
      padding:0 10px; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(19, 124, 189, 0.2); }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      top:0;
      right:0;
      bottom:0;
      left:0;
      border-radius:3px;
      background-color:rgba(19, 124, 189, 0.2);
      height:auto; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  position:relative;
  margin:0;
  border:none;
  padding:0;
  list-style:none; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  cursor:pointer;
  max-width:100%;
  vertical-align:top;
  line-height:30px;
  color:#182026;
  font-size:14px; }
  .bp3-tab a{
    display:block;
    text-decoration:none;
    color:inherit; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    background-color:transparent !important; }
  .bp3-tab[aria-disabled="true"]{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    line-height:40px;
    font-size:16px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  position:absolute;
  top:0;
  left:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
  pointer-events:none; }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    position:absolute;
    right:0;
    bottom:0;
    left:0;
    background-color:#106ba3;
    height:3px; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:#5c7080;
  min-width:20px;
  max-width:100%;
  min-height:20px;
  padding:2px 6px;
  line-height:16px;
  color:#f5f8fa;
  font-size:12px; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-right:8px;
    padding-left:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    min-width:30px;
    min-height:30px;
    padding:0 10px;
    line-height:20px;
    font-size:14px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-right:12px;
      padding-left:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  opacity:0.5;
  margin-top:-2px;
  margin-right:-6px !important;
  margin-bottom:-2px;
  border:none;
  background:none;
  cursor:pointer;
  padding:2px;
  padding-left:0;
  color:inherit; }
  .bp3-tag-remove:hover{
    opacity:0.8;
    background:none;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:5px;
    padding-left:0; }
    .bp3-large .bp3-tag-remove:empty::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  min-height:30px;
  padding-right:0;
  padding-left:5px;
  line-height:inherit; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    margin-top:7px;
    margin-right:7px;
    margin-left:2px;
    color:#5c7080; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    margin-top:5px;
    margin-right:7px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:80px;
    line-height:20px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-top:10px;
      margin-left:5px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-width:30px;
      min-height:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  position:relative !important;
  margin:20px 0 0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  min-width:300px;
  max-width:500px;
  pointer-events:all; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:50ms;
            transition-delay:50ms; }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    margin:12px;
    margin-right:0;
    color:#5c7080; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
    background-color:#394b59; }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:fixed;
  right:0;
  left:0;
  z-index:40;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0;
    bottom:auto; }
  .bp3-toast-container.bp3-toast-container-bottom{
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto;
    bottom:0; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    position:absolute;
    width:22px;
    height:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      margin:4px;
      width:14px;
      height:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-top:-11px;
    margin-bottom:11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-right:11px;
    margin-left:-11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  margin:0;
  padding-left:0;
  list-style:none; }

.bp3-tree-root{
  position:relative;
  background-color:transparent;
  cursor:default;
  padding-left:0; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  width:100%;
  height:30px;
  padding-right:5px; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  cursor:pointer;
  padding:7px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  position:relative;
  margin-right:7px; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
/*!

Copyright 2017-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  top:20vh;
  left:calc(50% - 250px);
  z-index:21;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:500px; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar .bp3-input{
    border-radius:0;
    background-color:transparent; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    background-color:transparent;
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDhoLTIuODFjLS40NS0uNzgtMS4wNy0xLjQ1LTEuODItMS45NkwxNyA0LjQxIDE1LjU5IDNsLTIuMTcgMi4xN0MxMi45NiA1LjA2IDEyLjQ5IDUgMTIgNWMtLjQ5IDAtLjk2LjA2LTEuNDEuMTdMOC40MSAzIDcgNC40MWwxLjYyIDEuNjNDNy44OCA2LjU1IDcuMjYgNy4yMiA2LjgxIDhINHYyaDIuMDljLS4wNS4zMy0uMDkuNjYtLjA5IDF2MUg0djJoMnYxYzAgLjM0LjA0LjY3LjA5IDFINHYyaDIuODFjMS4wNCAxLjc5IDIuOTcgMyA1LjE5IDNzNC4xNS0xLjIxIDUuMTktM0gyMHYtMmgtMi4wOWMuMDUtLjMzLjA5LS42Ni4wOS0xdi0xaDJ2LTJoLTJ2LTFjMC0uMzQtLjA0LS42Ny0uMDktMUgyMFY4em0tNiA4aC00di0yaDR2MnptMC00aC00di0yaDR2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTYuMTdMNC44MyAxMmwtMS40MiAxLjQxTDkgMTkgMjEgN2wtMS40MS0xLjQxeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJDYXBhXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4Ig0KCSB2aWV3Qm94PSIwIDAgNTAuOTc4IDUwLjk3OCIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTAuOTc4IDUwLjk3ODsiIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPGc+DQoJCTxnPg0KCQkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik00My41Miw3LjQ1OEMzOC43MTEsMi42NDgsMzIuMzA3LDAsMjUuNDg5LDBDMTguNjcsMCwxMi4yNjYsMi42NDgsNy40NTgsNy40NTgNCgkJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDANCgkJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoNCgkJCQkgTTQyLjEwNiw0Mi4xMDVjLTQuNDMyLDQuNDMxLTEwLjMzMiw2Ljg3Mi0xNi42MTUsNi44NzJoLTAuMDAyYy02LjI4NS0wLjAwMS0xMi4xODctMi40NDEtMTYuNjE3LTYuODcyDQoJCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzINCgkJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4NCgkJPC9nPg0KCQk8Zz4NCgkJCTxwYXRoIHN0eWxlPSJmaWxsOiMwMTAwMDI7IiBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1Mw0KCQkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUNCgkJCQljMC0xLjA5Ni0wLjI2LTIuMDg4LTAuNzc5LTIuOTc5Yy0wLjU2NS0wLjg3OS0xLjUwMS0xLjMzNi0yLjgwNi0xLjM2OWMtMS44MDIsMC4wNTctMi45ODUsMC42NjctMy41NSwxLjgzMg0KCQkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkNCgkJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQ0KCQkJCWMwLDEuMTQyLTAuMTM3LDIuMTExLTAuNDEsMi45MTFjLTAuMzA5LDAuODQ1LTAuNzMxLDEuNTkzLTEuMjY4LDIuMjQzYy0wLjQ5MiwwLjY1LTEuMDY4LDEuMzE4LTEuNzMsMi4wMDINCgkJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5DQoJCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+DQoJCTwvZz4NCgk8L2c+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8L3N2Zz4NCg==);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

:root {
  --jp-icon-search-white: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
}

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.lm-CommandPalette-wrapper::after {
  content: ' ';
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  height: 30px;
  width: 10px;
  padding: 0px 10px;
  background-image: var(--jp-icon-search-white);
  background-size: 20px;
  background-repeat: no-repeat;
  background-position: center;
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color3);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item.lm-mod-active {
  background: var(--jp-layout-color3);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  background: var(--jp-layout-color4);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.4;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

.jp-Dialog-header {
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 30px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -30px; margin-right: -30px;
  padding-bottom: 30px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 30px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -30px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*
  Name:       material
  Author:     Mattia Astorino (http://github.com/equinusocio)
  Website:    https://material-theme.site/
*/

.cm-s-material.CodeMirror {
  background-color: #263238;
  color: #EEFFFF;
}

.cm-s-material .CodeMirror-gutters {
  background: #263238;
  color: #546E7A;
  border: none;
}

.cm-s-material .CodeMirror-guttermarker,
.cm-s-material .CodeMirror-guttermarker-subtle,
.cm-s-material .CodeMirror-linenumber {
  color: #546E7A;
}

.cm-s-material .CodeMirror-cursor {
  border-left: 1px solid #FFCC00;
}

.cm-s-material div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material.CodeMirror-focused div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::selection,
.cm-s-material .CodeMirror-line>span::selection,
.cm-s-material .CodeMirror-line>span>span::selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::-moz-selection,
.cm-s-material .CodeMirror-line>span::-moz-selection,
.cm-s-material .CodeMirror-line>span>span::-moz-selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.5);
}

.cm-s-material .cm-keyword {
  color: #C792EA;
}

.cm-s-material .cm-operator {
  color: #89DDFF;
}

.cm-s-material .cm-variable-2 {
  color: #EEFFFF;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #f07178;
}

.cm-s-material .cm-builtin {
  color: #FFCB6B;
}

.cm-s-material .cm-atom {
  color: #F78C6C;
}

.cm-s-material .cm-number {
  color: #FF5370;
}

.cm-s-material .cm-def {
  color: #82AAFF;
}

.cm-s-material .cm-string {
  color: #C3E88D;
}

.cm-s-material .cm-string-2 {
  color: #f07178;
}

.cm-s-material .cm-comment {
  color: #546E7A;
}

.cm-s-material .cm-variable {
  color: #f07178;
}

.cm-s-material .cm-tag {
  color: #FF5370;
}

.cm-s-material .cm-meta {
  color: #FFCB6B;
}

.cm-s-material .cm-attribute {
  color: #C792EA;
}

.cm-s-material .cm-property {
  color: #C792EA;
}

.cm-s-material .cm-qualifier {
  color: #DECB6B;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #DECB6B;
}


.cm-s-material .cm-error {
  color: rgba(255, 255, 255, 1.0);
  background-color: #FF5370;
}

.cm-s-material .CodeMirror-matchingbracket {
  text-decoration: underline;
  color: white !important;
}
/**
 * "
 *  Using Zenburn color palette from the Emacs Zenburn Theme
 *  https://github.com/bbatsov/zenburn-emacs/blob/master/zenburn-theme.el
 *
 *  Also using parts of https://github.com/xavi/coderay-lighttable-theme
 * "
 * From: https://github.com/wisenomad/zenburn-lighttable-theme/blob/master/zenburn.css
 */

.cm-s-zenburn .CodeMirror-gutters { background: #3f3f3f !important; }
.cm-s-zenburn .CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded { color: #999; }
.cm-s-zenburn .CodeMirror-cursor { border-left: 1px solid white; }
.cm-s-zenburn { background-color: #3f3f3f; color: #dcdccc; }
.cm-s-zenburn span.cm-builtin { color: #dcdccc; font-weight: bold; }
.cm-s-zenburn span.cm-comment { color: #7f9f7f; }
.cm-s-zenburn span.cm-keyword { color: #f0dfaf; font-weight: bold; }
.cm-s-zenburn span.cm-atom { color: #bfebbf; }
.cm-s-zenburn span.cm-def { color: #dcdccc; }
.cm-s-zenburn span.cm-variable { color: #dfaf8f; }
.cm-s-zenburn span.cm-variable-2 { color: #dcdccc; }
.cm-s-zenburn span.cm-string { color: #cc9393; }
.cm-s-zenburn span.cm-string-2 { color: #cc9393; }
.cm-s-zenburn span.cm-number { color: #dcdccc; }
.cm-s-zenburn span.cm-tag { color: #93e0e3; }
.cm-s-zenburn span.cm-property { color: #dfaf8f; }
.cm-s-zenburn span.cm-attribute { color: #dfaf8f; }
.cm-s-zenburn span.cm-qualifier { color: #7cb8bb; }
.cm-s-zenburn span.cm-meta { color: #f0dfaf; }
.cm-s-zenburn span.cm-header { color: #f0efd0; }
.cm-s-zenburn span.cm-operator { color: #f0efd0; }
.cm-s-zenburn span.CodeMirror-matchingbracket { box-sizing: border-box; background: transparent; border-bottom: 1px solid; }
.cm-s-zenburn span.CodeMirror-nonmatchingbracket { border-bottom: 1px solid; background: none; }
.cm-s-zenburn .CodeMirror-activeline { background: #000000; }
.cm-s-zenburn .CodeMirror-activeline-background { background: #000000; }
.cm-s-zenburn div.CodeMirror-selected { background: #545454; }
.cm-s-zenburn .CodeMirror-focused div.CodeMirror-selected { background: #4f4f4f; }

.cm-s-abcdef.CodeMirror { background: #0f0f0f; color: #defdef; }
.cm-s-abcdef div.CodeMirror-selected { background: #515151; }
.cm-s-abcdef .CodeMirror-line::selection, .cm-s-abcdef .CodeMirror-line > span::selection, .cm-s-abcdef .CodeMirror-line > span > span::selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-line::-moz-selection, .cm-s-abcdef .CodeMirror-line > span::-moz-selection, .cm-s-abcdef .CodeMirror-line > span > span::-moz-selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-gutters { background: #555; border-right: 2px solid #314151; }
.cm-s-abcdef .CodeMirror-guttermarker { color: #222; }
.cm-s-abcdef .CodeMirror-guttermarker-subtle { color: azure; }
.cm-s-abcdef .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-abcdef .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-abcdef span.cm-keyword { color: darkgoldenrod; font-weight: bold; }
.cm-s-abcdef span.cm-atom { color: #77F; }
.cm-s-abcdef span.cm-number { color: violet; }
.cm-s-abcdef span.cm-def { color: #fffabc; }
.cm-s-abcdef span.cm-variable { color: #abcdef; }
.cm-s-abcdef span.cm-variable-2 { color: #cacbcc; }
.cm-s-abcdef span.cm-variable-3, .cm-s-abcdef span.cm-type { color: #def; }
.cm-s-abcdef span.cm-property { color: #fedcba; }
.cm-s-abcdef span.cm-operator { color: #ff0; }
.cm-s-abcdef span.cm-comment { color: #7a7b7c; font-style: italic;}
.cm-s-abcdef span.cm-string { color: #2b4; }
.cm-s-abcdef span.cm-meta { color: #C9F; }
.cm-s-abcdef span.cm-qualifier { color: #FFF700; }
.cm-s-abcdef span.cm-builtin { color: #30aabc; }
.cm-s-abcdef span.cm-bracket { color: #8a8a8a; }
.cm-s-abcdef span.cm-tag { color: #FFDD44; }
.cm-s-abcdef span.cm-attribute { color: #DDFF00; }
.cm-s-abcdef span.cm-error { color: #FF0000; }
.cm-s-abcdef span.cm-header { color: aquamarine; font-weight: bold; }
.cm-s-abcdef span.cm-link { color: blueviolet; }

.cm-s-abcdef .CodeMirror-activeline-background { background: #314151; }

/*

    Name:       Base16 Default Light
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-light.CodeMirror { background: #f5f5f5; color: #202020; }
.cm-s-base16-light div.CodeMirror-selected { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::selection, .cm-s-base16-light .CodeMirror-line > span::selection, .cm-s-base16-light .CodeMirror-line > span > span::selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::-moz-selection, .cm-s-base16-light .CodeMirror-line > span::-moz-selection, .cm-s-base16-light .CodeMirror-line > span > span::-moz-selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-gutters { background: #f5f5f5; border-right: 0px; }
.cm-s-base16-light .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-light .CodeMirror-guttermarker-subtle { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-linenumber { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-cursor { border-left: 1px solid #505050; }

.cm-s-base16-light span.cm-comment { color: #8f5536; }
.cm-s-base16-light span.cm-atom { color: #aa759f; }
.cm-s-base16-light span.cm-number { color: #aa759f; }

.cm-s-base16-light span.cm-property, .cm-s-base16-light span.cm-attribute { color: #90a959; }
.cm-s-base16-light span.cm-keyword { color: #ac4142; }
.cm-s-base16-light span.cm-string { color: #f4bf75; }

.cm-s-base16-light span.cm-variable { color: #90a959; }
.cm-s-base16-light span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-light span.cm-def { color: #d28445; }
.cm-s-base16-light span.cm-bracket { color: #202020; }
.cm-s-base16-light span.cm-tag { color: #ac4142; }
.cm-s-base16-light span.cm-link { color: #aa759f; }
.cm-s-base16-light span.cm-error { background: #ac4142; color: #505050; }

.cm-s-base16-light .CodeMirror-activeline-background { background: #DDDCDC; }
.cm-s-base16-light .CodeMirror-matchingbracket { color: #f5f5f5 !important; background-color: #6A9FB5 !important}

/*

    Name:       Base16 Default Dark
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-dark.CodeMirror { background: #151515; color: #e0e0e0; }
.cm-s-base16-dark div.CodeMirror-selected { background: #303030; }
.cm-s-base16-dark .CodeMirror-line::selection, .cm-s-base16-dark .CodeMirror-line > span::selection, .cm-s-base16-dark .CodeMirror-line > span > span::selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-line::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-gutters { background: #151515; border-right: 0px; }
.cm-s-base16-dark .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-dark .CodeMirror-guttermarker-subtle { color: #505050; }
.cm-s-base16-dark .CodeMirror-linenumber { color: #505050; }
.cm-s-base16-dark .CodeMirror-cursor { border-left: 1px solid #b0b0b0; }

.cm-s-base16-dark span.cm-comment { color: #8f5536; }
.cm-s-base16-dark span.cm-atom { color: #aa759f; }
.cm-s-base16-dark span.cm-number { color: #aa759f; }

.cm-s-base16-dark span.cm-property, .cm-s-base16-dark span.cm-attribute { color: #90a959; }
.cm-s-base16-dark span.cm-keyword { color: #ac4142; }
.cm-s-base16-dark span.cm-string { color: #f4bf75; }

.cm-s-base16-dark span.cm-variable { color: #90a959; }
.cm-s-base16-dark span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-dark span.cm-def { color: #d28445; }
.cm-s-base16-dark span.cm-bracket { color: #e0e0e0; }
.cm-s-base16-dark span.cm-tag { color: #ac4142; }
.cm-s-base16-dark span.cm-link { color: #aa759f; }
.cm-s-base16-dark span.cm-error { background: #ac4142; color: #b0b0b0; }

.cm-s-base16-dark .CodeMirror-activeline-background { background: #202020; }
.cm-s-base16-dark .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       dracula
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original dracula color scheme by Zeno Rocha (https://github.com/zenorocha/dracula-theme)

*/


.cm-s-dracula.CodeMirror, .cm-s-dracula .CodeMirror-gutters {
  background-color: #282a36 !important;
  color: #f8f8f2 !important;
  border: none;
}
.cm-s-dracula .CodeMirror-gutters { color: #282a36; }
.cm-s-dracula .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-dracula .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-dracula .CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::selection, .cm-s-dracula .CodeMirror-line > span::selection, .cm-s-dracula .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::-moz-selection, .cm-s-dracula .CodeMirror-line > span::-moz-selection, .cm-s-dracula .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula span.cm-comment { color: #6272a4; }
.cm-s-dracula span.cm-string, .cm-s-dracula span.cm-string-2 { color: #f1fa8c; }
.cm-s-dracula span.cm-number { color: #bd93f9; }
.cm-s-dracula span.cm-variable { color: #50fa7b; }
.cm-s-dracula span.cm-variable-2 { color: white; }
.cm-s-dracula span.cm-def { color: #50fa7b; }
.cm-s-dracula span.cm-operator { color: #ff79c6; }
.cm-s-dracula span.cm-keyword { color: #ff79c6; }
.cm-s-dracula span.cm-atom { color: #bd93f9; }
.cm-s-dracula span.cm-meta { color: #f8f8f2; }
.cm-s-dracula span.cm-tag { color: #ff79c6; }
.cm-s-dracula span.cm-attribute { color: #50fa7b; }
.cm-s-dracula span.cm-qualifier { color: #50fa7b; }
.cm-s-dracula span.cm-property { color: #66d9ef; }
.cm-s-dracula span.cm-builtin { color: #50fa7b; }
.cm-s-dracula span.cm-variable-3, .cm-s-dracula span.cm-type { color: #ffb86c; }

.cm-s-dracula .CodeMirror-activeline-background { background: rgba(255,255,255,0.1); }
.cm-s-dracula .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       Hopscotch
    Author:     Jan T. Sott

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-hopscotch.CodeMirror {background: #322931; color: #d5d3d5;}
.cm-s-hopscotch div.CodeMirror-selected {background: #433b42 !important;}
.cm-s-hopscotch .CodeMirror-gutters {background: #322931; border-right: 0px;}
.cm-s-hopscotch .CodeMirror-linenumber {color: #797379;}
.cm-s-hopscotch .CodeMirror-cursor {border-left: 1px solid #989498 !important;}

.cm-s-hopscotch span.cm-comment {color: #b33508;}
.cm-s-hopscotch span.cm-atom {color: #c85e7c;}
.cm-s-hopscotch span.cm-number {color: #c85e7c;}

.cm-s-hopscotch span.cm-property, .cm-s-hopscotch span.cm-attribute {color: #8fc13e;}
.cm-s-hopscotch span.cm-keyword {color: #dd464c;}
.cm-s-hopscotch span.cm-string {color: #fdcc59;}

.cm-s-hopscotch span.cm-variable {color: #8fc13e;}
.cm-s-hopscotch span.cm-variable-2 {color: #1290bf;}
.cm-s-hopscotch span.cm-def {color: #fd8b19;}
.cm-s-hopscotch span.cm-error {background: #dd464c; color: #989498;}
.cm-s-hopscotch span.cm-bracket {color: #d5d3d5;}
.cm-s-hopscotch span.cm-tag {color: #dd464c;}
.cm-s-hopscotch span.cm-link {color: #c85e7c;}

.cm-s-hopscotch .CodeMirror-matchingbracket { text-decoration: underline; color: white !important;}
.cm-s-hopscotch .CodeMirror-activeline-background { background: #302020; }

/****************************************************************/
/*   Based on mbonaci's Brackets mbo theme                      */
/*   https://github.com/mbonaci/global/blob/master/Mbo.tmTheme  */
/*   Create your own: http://tmtheme-editor.herokuapp.com       */
/****************************************************************/

.cm-s-mbo.CodeMirror { background: #2c2c2c; color: #ffffec; }
.cm-s-mbo div.CodeMirror-selected { background: #716C62; }
.cm-s-mbo .CodeMirror-line::selection, .cm-s-mbo .CodeMirror-line > span::selection, .cm-s-mbo .CodeMirror-line > span > span::selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-line::-moz-selection, .cm-s-mbo .CodeMirror-line > span::-moz-selection, .cm-s-mbo .CodeMirror-line > span > span::-moz-selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-gutters { background: #4e4e4e; border-right: 0px; }
.cm-s-mbo .CodeMirror-guttermarker { color: white; }
.cm-s-mbo .CodeMirror-guttermarker-subtle { color: grey; }
.cm-s-mbo .CodeMirror-linenumber { color: #dadada; }
.cm-s-mbo .CodeMirror-cursor { border-left: 1px solid #ffffec; }

.cm-s-mbo span.cm-comment { color: #95958a; }
.cm-s-mbo span.cm-atom { color: #00a8c6; }
.cm-s-mbo span.cm-number { color: #00a8c6; }

.cm-s-mbo span.cm-property, .cm-s-mbo span.cm-attribute { color: #9ddfe9; }
.cm-s-mbo span.cm-keyword { color: #ffb928; }
.cm-s-mbo span.cm-string { color: #ffcf6c; }
.cm-s-mbo span.cm-string.cm-property { color: #ffffec; }

.cm-s-mbo span.cm-variable { color: #ffffec; }
.cm-s-mbo span.cm-variable-2 { color: #00a8c6; }
.cm-s-mbo span.cm-def { color: #ffffec; }
.cm-s-mbo span.cm-bracket { color: #fffffc; font-weight: bold; }
.cm-s-mbo span.cm-tag { color: #9ddfe9; }
.cm-s-mbo span.cm-link { color: #f54b07; }
.cm-s-mbo span.cm-error { border-bottom: #636363; color: #ffffec; }
.cm-s-mbo span.cm-qualifier { color: #ffffec; }

.cm-s-mbo .CodeMirror-activeline-background { background: #494b41; }
.cm-s-mbo .CodeMirror-matchingbracket { color: #ffb928 !important; }
.cm-s-mbo .CodeMirror-matchingtag { background: rgba(255, 255, 255, .37); }

/*
  MDN-LIKE Theme - Mozilla
  Ported to CodeMirror by Peter Kroon <plakroon@gmail.com>
  Report bugs/issues here: https://github.com/codemirror/CodeMirror/issues
  GitHub: @peterkroon

  The mdn-like theme is inspired on the displayed code examples at: https://developer.mozilla.org/en-US/docs/Web/CSS/animation

*/
.cm-s-mdn-like.CodeMirror { color: #999; background-color: #fff; }
.cm-s-mdn-like div.CodeMirror-selected { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::selection, .cm-s-mdn-like .CodeMirror-line > span::selection, .cm-s-mdn-like .CodeMirror-line > span > span::selection { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span > span::-moz-selection { background: #cfc; }

.cm-s-mdn-like .CodeMirror-gutters { background: #f8f8f8; border-left: 6px solid rgba(0,83,159,0.65); color: #333; }
.cm-s-mdn-like .CodeMirror-linenumber { color: #aaa; padding-left: 8px; }
.cm-s-mdn-like .CodeMirror-cursor { border-left: 2px solid #222; }

.cm-s-mdn-like .cm-keyword { color: #6262FF; }
.cm-s-mdn-like .cm-atom { color: #F90; }
.cm-s-mdn-like .cm-number { color:  #ca7841; }
.cm-s-mdn-like .cm-def { color: #8DA6CE; }
.cm-s-mdn-like span.cm-variable-2, .cm-s-mdn-like span.cm-tag { color: #690; }
.cm-s-mdn-like span.cm-variable-3, .cm-s-mdn-like span.cm-def, .cm-s-mdn-like span.cm-type { color: #07a; }

.cm-s-mdn-like .cm-variable { color: #07a; }
.cm-s-mdn-like .cm-property { color: #905; }
.cm-s-mdn-like .cm-qualifier { color: #690; }

.cm-s-mdn-like .cm-operator { color: #cda869; }
.cm-s-mdn-like .cm-comment { color:#777; font-weight:normal; }
.cm-s-mdn-like .cm-string { color:#07a; font-style:italic; }
.cm-s-mdn-like .cm-string-2 { color:#bd6b18; } /*?*/
.cm-s-mdn-like .cm-meta { color: #000; } /*?*/
.cm-s-mdn-like .cm-builtin { color: #9B7536; } /*?*/
.cm-s-mdn-like .cm-tag { color: #997643; }
.cm-s-mdn-like .cm-attribute { color: #d6bb6d; } /*?*/
.cm-s-mdn-like .cm-header { color: #FF6400; }
.cm-s-mdn-like .cm-hr { color: #AEAEAE; }
.cm-s-mdn-like .cm-link { color:#ad9361; font-style:italic; text-decoration:none; }
.cm-s-mdn-like .cm-error { border-bottom: 1px solid red; }

div.cm-s-mdn-like .CodeMirror-activeline-background { background: #efefff; }
div.cm-s-mdn-like span.CodeMirror-matchingbracket { outline:1px solid grey; color: inherit; }

.cm-s-mdn-like.CodeMirror { background-image: url(data:image/png;base64,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); }

/*

    Name:       seti
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original seti color scheme by Jesse Weed (https://github.com/jesseweed/seti-syntax)

*/


.cm-s-seti.CodeMirror {
  background-color: #151718 !important;
  color: #CFD2D1 !important;
  border: none;
}
.cm-s-seti .CodeMirror-gutters {
  color: #404b53;
  background-color: #0E1112;
  border: none;
}
.cm-s-seti .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-seti .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-seti.CodeMirror-focused div.CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::selection, .cm-s-seti .CodeMirror-line > span::selection, .cm-s-seti .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::-moz-selection, .cm-s-seti .CodeMirror-line > span::-moz-selection, .cm-s-seti .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti span.cm-comment { color: #41535b; }
.cm-s-seti span.cm-string, .cm-s-seti span.cm-string-2 { color: #55b5db; }
.cm-s-seti span.cm-number { color: #cd3f45; }
.cm-s-seti span.cm-variable { color: #55b5db; }
.cm-s-seti span.cm-variable-2 { color: #a074c4; }
.cm-s-seti span.cm-def { color: #55b5db; }
.cm-s-seti span.cm-keyword { color: #ff79c6; }
.cm-s-seti span.cm-operator { color: #9fca56; }
.cm-s-seti span.cm-keyword { color: #e6cd69; }
.cm-s-seti span.cm-atom { color: #cd3f45; }
.cm-s-seti span.cm-meta { color: #55b5db; }
.cm-s-seti span.cm-tag { color: #55b5db; }
.cm-s-seti span.cm-attribute { color: #9fca56; }
.cm-s-seti span.cm-qualifier { color: #9fca56; }
.cm-s-seti span.cm-property { color: #a074c4; }
.cm-s-seti span.cm-variable-3, .cm-s-seti span.cm-type { color: #9fca56; }
.cm-s-seti span.cm-builtin { color: #9fca56; }
.cm-s-seti .CodeMirror-activeline-background { background: #101213; }
.cm-s-seti .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*
Solarized theme for code-mirror
http://ethanschoonover.com/solarized
*/

/*
Solarized color palette
http://ethanschoonover.com/solarized/img/solarized-palette.png
*/

.solarized.base03 { color: #002b36; }
.solarized.base02 { color: #073642; }
.solarized.base01 { color: #586e75; }
.solarized.base00 { color: #657b83; }
.solarized.base0 { color: #839496; }
.solarized.base1 { color: #93a1a1; }
.solarized.base2 { color: #eee8d5; }
.solarized.base3  { color: #fdf6e3; }
.solarized.solar-yellow  { color: #b58900; }
.solarized.solar-orange  { color: #cb4b16; }
.solarized.solar-red { color: #dc322f; }
.solarized.solar-magenta { color: #d33682; }
.solarized.solar-violet  { color: #6c71c4; }
.solarized.solar-blue { color: #268bd2; }
.solarized.solar-cyan { color: #2aa198; }
.solarized.solar-green { color: #859900; }

/* Color scheme for code-mirror */

.cm-s-solarized {
  line-height: 1.45em;
  color-profile: sRGB;
  rendering-intent: auto;
}
.cm-s-solarized.cm-s-dark {
  color: #839496;
  background-color: #002b36;
  text-shadow: #002b36 0 1px;
}
.cm-s-solarized.cm-s-light {
  background-color: #fdf6e3;
  color: #657b83;
  text-shadow: #eee8d5 0 1px;
}

.cm-s-solarized .CodeMirror-widget {
  text-shadow: none;
}

.cm-s-solarized .cm-header { color: #586e75; }
.cm-s-solarized .cm-quote { color: #93a1a1; }

.cm-s-solarized .cm-keyword { color: #cb4b16; }
.cm-s-solarized .cm-atom { color: #d33682; }
.cm-s-solarized .cm-number { color: #d33682; }
.cm-s-solarized .cm-def { color: #2aa198; }

.cm-s-solarized .cm-variable { color: #839496; }
.cm-s-solarized .cm-variable-2 { color: #b58900; }
.cm-s-solarized .cm-variable-3, .cm-s-solarized .cm-type { color: #6c71c4; }

.cm-s-solarized .cm-property { color: #2aa198; }
.cm-s-solarized .cm-operator { color: #6c71c4; }

.cm-s-solarized .cm-comment { color: #586e75; font-style:italic; }

.cm-s-solarized .cm-string { color: #859900; }
.cm-s-solarized .cm-string-2 { color: #b58900; }

.cm-s-solarized .cm-meta { color: #859900; }
.cm-s-solarized .cm-qualifier { color: #b58900; }
.cm-s-solarized .cm-builtin { color: #d33682; }
.cm-s-solarized .cm-bracket { color: #cb4b16; }
.cm-s-solarized .CodeMirror-matchingbracket { color: #859900; }
.cm-s-solarized .CodeMirror-nonmatchingbracket { color: #dc322f; }
.cm-s-solarized .cm-tag { color: #93a1a1; }
.cm-s-solarized .cm-attribute { color: #2aa198; }
.cm-s-solarized .cm-hr {
  color: transparent;
  border-top: 1px solid #586e75;
  display: block;
}
.cm-s-solarized .cm-link { color: #93a1a1; cursor: pointer; }
.cm-s-solarized .cm-special { color: #6c71c4; }
.cm-s-solarized .cm-em {
  color: #999;
  text-decoration: underline;
  text-decoration-style: dotted;
}
.cm-s-solarized .cm-error,
.cm-s-solarized .cm-invalidchar {
  color: #586e75;
  border-bottom: 1px dotted #dc322f;
}

.cm-s-solarized.cm-s-dark div.CodeMirror-selected { background: #073642; }
.cm-s-solarized.cm-s-dark.CodeMirror ::selection { background: rgba(7, 54, 66, 0.99); }
.cm-s-solarized.cm-s-dark .CodeMirror-line::-moz-selection, .cm-s-dark .CodeMirror-line > span::-moz-selection, .cm-s-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(7, 54, 66, 0.99); }

.cm-s-solarized.cm-s-light div.CodeMirror-selected { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::selection, .cm-s-light .CodeMirror-line > span::selection, .cm-s-light .CodeMirror-line > span > span::selection { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::-moz-selection, .cm-s-ligh .CodeMirror-line > span::-moz-selection, .cm-s-ligh .CodeMirror-line > span > span::-moz-selection { background: #eee8d5; }

/* Editor styling */



/* Little shadow on the view-port of the buffer view */
.cm-s-solarized.CodeMirror {
  -moz-box-shadow: inset 7px 0 12px -6px #000;
  -webkit-box-shadow: inset 7px 0 12px -6px #000;
  box-shadow: inset 7px 0 12px -6px #000;
}

/* Remove gutter border */
.cm-s-solarized .CodeMirror-gutters {
  border-right: 0;
}

/* Gutter colors and line number styling based of color scheme (dark / light) */

/* Dark */
.cm-s-solarized.cm-s-dark .CodeMirror-gutters {
  background-color: #073642;
}

.cm-s-solarized.cm-s-dark .CodeMirror-linenumber {
  color: #586e75;
  text-shadow: #021014 0 -1px;
}

/* Light */
.cm-s-solarized.cm-s-light .CodeMirror-gutters {
  background-color: #eee8d5;
}

.cm-s-solarized.cm-s-light .CodeMirror-linenumber {
  color: #839496;
}

/* Common */
.cm-s-solarized .CodeMirror-linenumber {
  padding: 0 5px;
}
.cm-s-solarized .CodeMirror-guttermarker-subtle { color: #586e75; }
.cm-s-solarized.cm-s-dark .CodeMirror-guttermarker { color: #ddd; }
.cm-s-solarized.cm-s-light .CodeMirror-guttermarker { color: #cb4b16; }

.cm-s-solarized .CodeMirror-gutter .CodeMirror-gutter-text {
  color: #586e75;
}

/* Cursor */
.cm-s-solarized .CodeMirror-cursor { border-left: 1px solid #819090; }

/* Fat cursor */
.cm-s-solarized.cm-s-light.cm-fat-cursor .CodeMirror-cursor { background: #77ee77; }
.cm-s-solarized.cm-s-light .cm-animate-fat-cursor { background-color: #77ee77; }
.cm-s-solarized.cm-s-dark.cm-fat-cursor .CodeMirror-cursor { background: #586e75; }
.cm-s-solarized.cm-s-dark .cm-animate-fat-cursor { background-color: #586e75; }

/* Active line */
.cm-s-solarized.cm-s-dark .CodeMirror-activeline-background {
  background: rgba(255, 255, 255, 0.06);
}
.cm-s-solarized.cm-s-light .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.06);
}

.cm-s-the-matrix.CodeMirror { background: #000000; color: #00FF00; }
.cm-s-the-matrix div.CodeMirror-selected { background: #2D2D2D; }
.cm-s-the-matrix .CodeMirror-line::selection, .cm-s-the-matrix .CodeMirror-line > span::selection, .cm-s-the-matrix .CodeMirror-line > span > span::selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-line::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span > span::-moz-selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-gutters { background: #060; border-right: 2px solid #00FF00; }
.cm-s-the-matrix .CodeMirror-guttermarker { color: #0f0; }
.cm-s-the-matrix .CodeMirror-guttermarker-subtle { color: white; }
.cm-s-the-matrix .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-the-matrix .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-the-matrix span.cm-keyword { color: #008803; font-weight: bold; }
.cm-s-the-matrix span.cm-atom { color: #3FF; }
.cm-s-the-matrix span.cm-number { color: #FFB94F; }
.cm-s-the-matrix span.cm-def { color: #99C; }
.cm-s-the-matrix span.cm-variable { color: #F6C; }
.cm-s-the-matrix span.cm-variable-2 { color: #C6F; }
.cm-s-the-matrix span.cm-variable-3, .cm-s-the-matrix span.cm-type { color: #96F; }
.cm-s-the-matrix span.cm-property { color: #62FFA0; }
.cm-s-the-matrix span.cm-operator { color: #999; }
.cm-s-the-matrix span.cm-comment { color: #CCCCCC; }
.cm-s-the-matrix span.cm-string { color: #39C; }
.cm-s-the-matrix span.cm-meta { color: #C9F; }
.cm-s-the-matrix span.cm-qualifier { color: #FFF700; }
.cm-s-the-matrix span.cm-builtin { color: #30a; }
.cm-s-the-matrix span.cm-bracket { color: #cc7; }
.cm-s-the-matrix span.cm-tag { color: #FFBD40; }
.cm-s-the-matrix span.cm-attribute { color: #FFF700; }
.cm-s-the-matrix span.cm-error { color: #FF0000; }

.cm-s-the-matrix .CodeMirror-activeline-background { background: #040; }

/*
Copyright (C) 2011 by MarkLogic Corporation
Author: Mike Brevoort <mike@brevoort.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
*/
.cm-s-xq-light span.cm-keyword { line-height: 1em; font-weight: bold; color: #5A5CAD; }
.cm-s-xq-light span.cm-atom { color: #6C8CD5; }
.cm-s-xq-light span.cm-number { color: #164; }
.cm-s-xq-light span.cm-def { text-decoration:underline; }
.cm-s-xq-light span.cm-variable { color: black; }
.cm-s-xq-light span.cm-variable-2 { color:black; }
.cm-s-xq-light span.cm-variable-3, .cm-s-xq-light span.cm-type { color: black; }
.cm-s-xq-light span.cm-property {}
.cm-s-xq-light span.cm-operator {}
.cm-s-xq-light span.cm-comment { color: #0080FF; font-style: italic; }
.cm-s-xq-light span.cm-string { color: red; }
.cm-s-xq-light span.cm-meta { color: yellow; }
.cm-s-xq-light span.cm-qualifier { color: grey; }
.cm-s-xq-light span.cm-builtin { color: #7EA656; }
.cm-s-xq-light span.cm-bracket { color: #cc7; }
.cm-s-xq-light span.cm-tag { color: #3F7F7F; }
.cm-s-xq-light span.cm-attribute { color: #7F007F; }
.cm-s-xq-light span.cm-error { color: #f00; }

.cm-s-xq-light .CodeMirror-activeline-background { background: #e8f2ff; }
.cm-s-xq-light .CodeMirror-matchingbracket { outline:1px solid grey;color:black !important;background:yellow; }

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor-static {
  margin: var(--jp-code-padding);
}

.jp-CodeMirrorEditor,
.jp-CodeMirrorEditor-static {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
  line-height: normal;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 4px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: space-evenly;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 1;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 100%;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item.jp-mod-selected {
  color: white;
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: limegreen;
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

.jp-FileDialog.jp-mod-conflict input {
  color: red;
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

.jp-OutputArea-executeResult.jp-RenderedText {
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: flex;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-700);
  --jp-brand-color1: var(--md-blue-500);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-700);
  --jp-accent-color1: var(--md-green-500);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-700);
  --jp-warn-color1: var(--md-orange-500);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-700);
  --jp-error-color1: var(--md-red-500);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-700);
  --jp-success-color1: var(--md-green-500);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-700);
  --jp-info-color1: var(--md-cyan-500);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: 'Source Code Pro', monospace;
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 180px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
a.anchor-link {
   display: none;
}
.highlight  {
    margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
    overflow: hidden;
}

.jp-InputArea-editor {
    overflow: hidden;
}

@media print {
  body {
    margin: 0;
  }
}
</style>



<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: { 
                    automatic: true 
                    }
                },
                "HTML-CSS": {
                    linebreaks: { 
                    automatic: true 
                    }
                }
            });
        
            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Introduction"><strong>Introduction</strong><a class="anchor-link" href="#Introduction">&#182;</a></h1>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The following notebook focuses on imbalanced binary classification problems. Some real world scenarios that utilise machine learning solutions where such problems can be encountered are that of loan approval systems, credit risk analysis, etc where one label class dominates the other with regards to the number of observations. If not not handled carefully, data models won't perform as per the expectations. The project discusses some of the common errors and  how to avoid them.</p>
<p>Note: This notebook concentrates only on data modeling and does not contain any EDA.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p><strong>The goal:</strong> The problem that is going to be used to demonstrate the above concept is that of predicting customers of an Insurance company who have health insurances set up with that firm and would be interested in taking up automobile insurance as well. The company has recently expanded their services to include automobile insurance and would like to focus their resources and efforts on customers who are more likely to subscribe.</p>
<p><strong>Dataset used:</strong> The dataset that is is being used is from Kaggle. It can be found <a href="https://www.kaggle.com/datasets/arashnic/imbalanced-data-practice">here.</a> Credits to the person who compiled the dataset.</p>
<p>Let's get started!</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># import necessary libraries</span>

<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="kn">import</span> <span class="n">metrics</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">StandardScaler</span><span class="p">,</span> <span class="n">LabelEncoder</span><span class="p">,</span> <span class="n">OneHotEncoder</span><span class="p">,</span> <span class="n">MinMaxScaler</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span><span class="p">,</span> <span class="n">GridSearchCV</span><span class="p">,</span> <span class="n">StratifiedKFold</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">confusion_matrix</span><span class="p">,</span> <span class="n">classification_report</span>
<span class="kn">from</span> <span class="nn">sklearn.metrics</span> <span class="kn">import</span> <span class="n">precision_score</span><span class="p">,</span> <span class="n">recall_score</span><span class="p">,</span> <span class="n">f1_score</span><span class="p">,</span> <span class="n">accuracy_score</span>
<span class="kn">from</span> <span class="nn">imblearn.over_sampling</span> <span class="kn">import</span> <span class="n">SMOTE</span>
<span class="kn">from</span> <span class="nn">imblearn.under_sampling</span> <span class="kn">import</span> <span class="n">RandomUnderSampler</span>
<span class="kn">from</span> <span class="nn">collections</span> <span class="kn">import</span> <span class="n">Counter</span>
<span class="kn">import</span> <span class="nn">warnings</span>
<span class="n">warnings</span><span class="o">.</span><span class="n">filterwarnings</span><span class="p">(</span><span class="s1">&#39;ignore&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Data-preprocessing"><strong>Data preprocessing</strong><a class="anchor-link" href="#Data-preprocessing">&#182;</a></h1>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>In this section, we are going to import the dataset and visualise it to understand the flavour of the data and the steps to process it for our final task, i.e. predicting if a customer will go for the automobile insurance or not. Most of the code in this section is self explanatory and easy to follow along.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># read data files (Enter your own respective file locations)</span>

<span class="n">df1</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;/content/drive/MyDrive/insurance_prediction/aug_train.csv&#39;</span><span class="p">)</span>
<span class="n">df2</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;/content/drive/MyDrive/insurance_prediction/aug_test.csv&#39;</span><span class="p">)</span>
<span class="n">ans</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">load</span><span class="p">(</span><span class="s1">&#39;/content/drive/MyDrive/insurance_prediction/answer.npy&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[15]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># I am going to combine both train and test sets with random shuffling to create a master dataset</span>

<span class="n">df2</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="n">ans</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df1</span><span class="p">,</span> <span class="n">df2</span><span class="p">])</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">frac</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">drop</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[16]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[16]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-8df9e567-a24f-4da0-a79f-b87f6137984b">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>Gender</th>
      <th>Age</th>
      <th>Driving_License</th>
      <th>Region_Code</th>
      <th>Previously_Insured</th>
      <th>Vehicle_Age</th>
      <th>Vehicle_Damage</th>
      <th>Annual_Premium</th>
      <th>Policy_Sales_Channel</th>
      <th>Vintage</th>
      <th>Response</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>250452</td>
      <td>Male</td>
      <td>35</td>
      <td>1</td>
      <td>28.0</td>
      <td>0</td>
      <td>1-2 Year</td>
      <td>Yes</td>
      <td>39183.0</td>
      <td>26.0</td>
      <td>142</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>366939</td>
      <td>Female</td>
      <td>49</td>
      <td>1</td>
      <td>37.0</td>
      <td>0</td>
      <td>1-2 Year</td>
      <td>Yes</td>
      <td>35649.0</td>
      <td>26.0</td>
      <td>178</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>185895</td>
      <td>Male</td>
      <td>36</td>
      <td>1</td>
      <td>28.0</td>
      <td>0</td>
      <td>1-2 Year</td>
      <td>Yes</td>
      <td>22364.0</td>
      <td>26.0</td>
      <td>145</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>454455</td>
      <td>Male</td>
      <td>38</td>
      <td>1</td>
      <td>41.0</td>
      <td>0</td>
      <td>&lt; 1 Year</td>
      <td>Yes</td>
      <td>2630.0</td>
      <td>157.0</td>
      <td>145</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>387968</td>
      <td>Female</td>
      <td>66</td>
      <td>1</td>
      <td>3.0</td>
      <td>1</td>
      <td>1-2 Year</td>
      <td>No</td>
      <td>15088.0</td>
      <td>26.0</td>
      <td>232</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-8df9e567-a24f-4da0-a79f-b87f6137984b')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-8df9e567-a24f-4da0-a79f-b87f6137984b button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-8df9e567-a24f-4da0-a79f-b87f6137984b');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">shape</span>    <span class="c1"># shape of the complete dataset</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>(460427, 12)</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">isna</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>     <span class="c1"># checking for null values</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>id                      0
Gender                  0
Age                     0
Driving_License         0
Region_Code             0
Previously_Insured      0
Vehicle_Age             0
Vehicle_Damage          0
Annual_Premium          0
Policy_Sales_Channel    0
Vintage                 0
Response                0
dtype: int64</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">nunique</span><span class="p">()</span>      <span class="c1"># checking number of unique values in each feature</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>id                      460427
Gender                       2
Age                         66
Driving_License              2
Region_Code                 53
Previously_Insured           2
Vehicle_Age                  3
Vehicle_Damage               2
Annual_Premium           51002
Policy_Sales_Channel       156
Vintage                    290
Response                     2
dtype: int64</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>There are 460427 unique rows in the dataset. I have reduced the number of rows by random sampling to speed up the training process as this task is only for demonstration. But the proportion of the number of positive labels to number of negative labels from the original dataset has been maintained. There are more elegant ways to do this but I have used a pretty straightforward method.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Size of dataframe&#39;</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">df</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Fraction not opting for vehicle insurance:&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">((</span><span class="n">Counter</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])[</span><span class="mi">0</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">df</span><span class="p">))</span><span class="o">*</span><span class="mi">100</span><span class="p">),</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Fraction opting for vehicle insurance:&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">((</span><span class="n">Counter</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])[</span><span class="mi">1</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">df</span><span class="p">))</span><span class="o">*</span><span class="mi">100</span><span class="p">),</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Size of dataframe 460427
Fraction not opting for vehicle insurance: 84 %
Fraction opting for vehicle insurance: 16 %
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[17]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">mdf1</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]</span><span class="o">==</span><span class="mi">0</span><span class="p">]</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">n</span><span class="o">=</span><span class="mi">8400</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">9</span><span class="p">)</span>
<span class="n">mdf2</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]</span><span class="o">==</span><span class="mi">1</span><span class="p">]</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">n</span><span class="o">=</span><span class="mi">1600</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">9</span><span class="p">)</span>
<span class="n">mdf</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">mdf1</span><span class="p">,</span> <span class="n">mdf2</span><span class="p">])</span><span class="o">.</span><span class="n">sample</span><span class="p">(</span><span class="n">frac</span><span class="o">=</span><span class="mi">1</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span><span class="o">.</span><span class="n">reset_index</span><span class="p">(</span><span class="n">drop</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Size of reduced dataframe&#39;</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">mdf</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Fraction not opting for vehicle insurance:&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">((</span><span class="n">Counter</span><span class="p">(</span><span class="n">mdf</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])[</span><span class="mi">0</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">mdf</span><span class="p">))</span><span class="o">*</span><span class="mi">100</span><span class="p">),</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Fraction opting for vehicle insurance:&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">((</span><span class="n">Counter</span><span class="p">(</span><span class="n">mdf</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])[</span><span class="mi">1</span><span class="p">]</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">mdf</span><span class="p">))</span><span class="o">*</span><span class="mi">100</span><span class="p">),</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Size of reduced dataframe 10000
Fraction not opting for vehicle insurance: 84 %
Fraction opting for vehicle insurance: 16 %
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Counter</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="n">Counter</span><span class="p">(</span><span class="n">df</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">values</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Responses in original dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Counter</span><span class="p">(</span><span class="n">mdf</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="n">Counter</span><span class="p">(</span><span class="n">mdf</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">values</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Responses in reduced dataset&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[18]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span> <span class="o">=</span> <span class="n">mdf</span><span class="o">.</span><span class="n">copy</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can clearly visualise the imbalance of the number of observations. 0 denotes the people who have not opted for automobile insurance from the insurance firm and 1 denotes those who have. It agrees with our intuition that only a small fraction of the original number of clients will agree to enroll themselves into a new scheme.</p>
<p>Although I had said before that there will not be any EDA in this project, it can be mentioned that certain features such as region code, vehicle age and policy sales channel can be important features to analyse for targeted advertisement and marketing to draw more customers. With that out of the way, let's carry on.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">shape</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>(10000, 12)</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[19]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;id&#39;</span><span class="p">],</span> <span class="n">inplace</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">categorical_features</span> <span class="o">=</span> <span class="p">[</span><span class="n">x</span> <span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">df</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">values</span> <span class="k">if</span> <span class="n">x</span> <span class="ow">not</span> <span class="ow">in</span> <span class="p">[</span><span class="s1">&#39;Age&#39;</span><span class="p">,</span> <span class="s1">&#39;Annual_Premium&#39;</span><span class="p">,</span> <span class="s1">&#39;Response&#39;</span><span class="p">]]</span>       <span class="c1"># defining categorcal features</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">get_dummies</span><span class="p">(</span><span class="n">df</span><span class="p">,</span> <span class="n">columns</span> <span class="o">=</span> <span class="n">categorical_features</span><span class="p">)</span>               <span class="c1"># a quicker way to encode categorical features than one-hot encoding</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[19]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-4cf31e61-ba33-464a-8e68-c21e85cfe11a">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Annual_Premium</th>
      <th>Response</th>
      <th>Gender_Female</th>
      <th>Gender_Male</th>
      <th>Driving_License_0</th>
      <th>Driving_License_1</th>
      <th>Region_Code_0.0</th>
      <th>Region_Code_1.0</th>
      <th>Region_Code_2.0</th>
      <th>...</th>
      <th>Vintage_290</th>
      <th>Vintage_291</th>
      <th>Vintage_292</th>
      <th>Vintage_293</th>
      <th>Vintage_294</th>
      <th>Vintage_295</th>
      <th>Vintage_296</th>
      <th>Vintage_297</th>
      <th>Vintage_298</th>
      <th>Vintage_299</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>31</td>
      <td>31737.0</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>67</td>
      <td>43707.0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>77</td>
      <td>2630.0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>24</td>
      <td>28204.0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>49</td>
      <td>47437.0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 451 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-4cf31e61-ba33-464a-8e68-c21e85cfe11a')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-4cf31e61-ba33-464a-8e68-c21e85cfe11a button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-4cf31e61-ba33-464a-8e68-c21e85cfe11a');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[20]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># define features and labels</span>

<span class="n">features</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="n">df</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">values</span><span class="p">)</span>
<span class="n">features</span><span class="o">.</span><span class="n">remove</span><span class="p">(</span><span class="s1">&#39;Response&#39;</span><span class="p">)</span>

<span class="n">labels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[21]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">features</span><span class="p">]</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">labels</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p><strong>Scaling the features:</strong> I have used min max scaler in this case to preserve the binary form of the data in the categorical features. Normally standard scaler should be used as the only 2 continuous distribution features (age and annual premium) do not have a defined minimum and maximum but it should be fine as it is being applied on the whole dataset. Problems may arise if first min-max scaler is used to 'fit-transform' training dataset and then 'transform' is applied on test. In that case, standard scaler can be applied to individual features such as df[feature] = scaler.fit_transform(df[feature])</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[22]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">scaler</span> <span class="o">=</span> <span class="n">MinMaxScaler</span><span class="p">(</span><span class="n">feature_range</span><span class="o">=</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">))</span>

<span class="n">scaled_X</span> <span class="o">=</span> <span class="n">scaler</span><span class="o">.</span><span class="n">fit_transform</span><span class="p">(</span><span class="n">X</span><span class="p">)</span>
<span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">scaled_X</span><span class="p">,</span> <span class="n">columns</span><span class="o">=</span><span class="n">X</span><span class="o">.</span><span class="n">columns</span><span class="o">.</span><span class="n">values</span><span class="p">)</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[22]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-d0fc0797-d244-4d11-8b91-027479aa3e59">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Annual_Premium</th>
      <th>Gender_Female</th>
      <th>Gender_Male</th>
      <th>Driving_License_0</th>
      <th>Driving_License_1</th>
      <th>Region_Code_0.0</th>
      <th>Region_Code_1.0</th>
      <th>Region_Code_2.0</th>
      <th>Region_Code_3.0</th>
      <th>...</th>
      <th>Vintage_290</th>
      <th>Vintage_291</th>
      <th>Vintage_292</th>
      <th>Vintage_293</th>
      <th>Vintage_294</th>
      <th>Vintage_295</th>
      <th>Vintage_296</th>
      <th>Vintage_297</th>
      <th>Vintage_298</th>
      <th>Vintage_299</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.171875</td>
      <td>0.124894</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.734375</td>
      <td>0.176256</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.890625</td>
      <td>0.000000</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.062500</td>
      <td>0.109735</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.453125</td>
      <td>0.192261</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 450 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d0fc0797-d244-4d11-8b91-027479aa3e59')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">
        
  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>
      
  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d0fc0797-d244-4d11-8b91-027479aa3e59 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d0fc0797-d244-4d11-8b91-027479aa3e59');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>
  
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Data-Modelling"><strong>Data Modelling</strong><a class="anchor-link" href="#Data-Modelling">&#182;</a></h1>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">X_train</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">scaled_X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.2</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">9</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Finally we have arrived at the data modelling part. The features and labels have been split into train and test. In the bar plot below, we can see that the proportion of imbalance between the label classes has been maintained after the split.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Counter</span><span class="p">(</span><span class="n">y_train</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="n">Counter</span><span class="p">(</span><span class="n">y_train</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">values</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Training set&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">subplot</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">2</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">Counter</span><span class="p">(</span><span class="n">y_test</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">keys</span><span class="p">(),</span><span class="n">Counter</span><span class="p">(</span><span class="n">y_test</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">])</span><span class="o">.</span><span class="n">values</span><span class="p">())</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">([</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Test set&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAjAAAAGzCAYAAAAxPS2EAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjcuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/bCgiHAAAACXBIWXMAAA9hAAAPYQGoP6dpAABJYElEQVR4nO3dfVhUdf4//udwMwOiMwjKjKyApKagqIkGs5ppEiOiq4kVRUqKmu6gq2ze8FkjRItC8x4ls8Q22NQ2LaFQhJRSREVJQyMtDDYbqBBGLLk9vz/8cb6OogkKw8Hn47rOJfN+v8457yPOuZ6eW5kgCAKIiIiIJMTC3AMgIiIiaioGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYumcvvvgievTo0ax5o6OjIZPJ7u+AiIio3WOAacdkMtldTQcPHjT3UCUvOTkZa9euNfcwiNqE1tz3/P7774iOjjbLfuzs2bOIjo7GxYsXW33dBMj4LqT264MPPjD5/P777yM9PR3//ve/TdqffPJJqNXqZq+npqYG9fX1UCgUTZ63trYWtbW1sLGxafb624Jx48bhm2++4Y6MCK237wGAX3/9FV27dsWrr76K6Ojoe1pWU3300Ud4+umn8cUXX2DkyJGtum4CrMw9AGo5L7zwgsnno0ePIj09/Zb2m/3+++/o0KHDXa/H2tq6WeMDACsrK1hZ8Z8hUXvS3H0PUVPwFNIDbuTIkejfvz9yc3MxYsQIdOjQAf/3f/8HAPjkk08QGBgIZ2dnKBQK9OzZE8uXL0ddXZ3JMm6+BubixYuQyWRYtWoVtmzZgp49e0KhUGDo0KE4fvy4ybyNXQMjk8kQHh6OPXv2oH///lAoFOjXrx/S0tJuGf/BgwcxZMgQ2NjYoGfPnnj77bfv+rqa8+fPIygoCBqNBjY2NujevTuCg4NRUVFhUvfBBx/A29sbtra2cHBwQHBwMIqLi03+DlNTU/Hjjz+Kh8abe00Q0YOivr4ea9euRb9+/WBjYwO1Wo2XXnoJly9fNqk7ceIEdDodunTpAltbW7i7u2P69OkAru9runbtCgBYtmyZ+P2705GYmpoaLFu2DL1794aNjQ0cHR0xfPhwpKenm9R9++23mDx5MhwcHGBjY4MhQ4bg008/FfsTExPx9NNPAwBGjRrFU/JmwP/6En777TcEBAQgODgYL7zwgnhINzExER07dkRERAQ6duyIzMxMREVFwWg0YuXKlX+63OTkZFy5cgUvvfQSZDIZ4uLiMGnSJPzwww9/etTmq6++wscff4y///3v6NSpE9avX4+goCAUFRXB0dERAHDq1CmMGTMG3bp1w7Jly1BXV4eYmBhxh3Yn1dXV0Ol0qKqqwty5c6HRaPDTTz8hJSUF5eXlUKlUAIDXXnsNr7zyCp555hnMmDEDv/zyCzZs2IARI0bg1KlTsLe3x7/+9S9UVFTgf//7H9asWQMA6Nix45+OgehB9tJLLyExMRHTpk3DvHnzUFhYiI0bN+LUqVM4fPgwrK2tUVpaCn9/f3Tt2hVLliyBvb09Ll68iI8//hgA0LVrV2zevBlz5szBU089hUmTJgEABgwYcNv1RkdHIzY2FjNmzMCjjz4Ko9GIEydO4OTJk3jyyScBAPn5+Rg2bBj+8pe/YMmSJbCzs8POnTsxceJE/Pe//8VTTz2FESNGYN68eVi/fj3+7//+Dx4eHgAg/kmtQKAHhl6vF27+lT/++OMCACEhIeGW+t9///2Wtpdeekno0KGDcO3aNbEtNDRUcHNzEz8XFhYKAARHR0ehrKxMbP/kk08EAMLevXvFtldfffWWMQEQ5HK5cOHCBbHt66+/FgAIGzZsENvGjx8vdOjQQfjpp5/EtvPnzwtWVla3LPNmp06dEgAIu3btum3NxYsXBUtLS+G1114zaT9z5oxgZWVl0h4YGGjyd0BE/8/N+54vv/xSACAkJSWZ1KWlpZm07969WwAgHD9+/LbL/uWXXwQAwquvvnpXYxk4cKAQGBh4x5rRo0cLXl5eJvu5+vp64a9//avQu3dvsW3Xrl0CAOGLL764q3XT/cVTSASFQoFp06bd0m5rayv+fOXKFfz666947LHH8Pvvv+Pbb7/90+U+++yz6Ny5s/j5scceAwD88MMPfzqvn58fevbsKX4eMGAAlEqlOG9dXR0OHDiAiRMnwtnZWazr1asXAgIC/nT5DUdY9u3bh99//73Rmo8//hj19fV45pln8Ouvv4qTRqNB79698cUXX/zpeojoVrt27YJKpcKTTz5p8t3y9vZGx44dxe+Wvb09ACAlJQU1NTX3Zd329vbIz8/H+fPnG+0vKytDZmYmnnnmGXG/9+uvv+K3336DTqfD+fPn8dNPP92XsdC9YYAh/OUvf4FcLr+lPT8/H0899RRUKhWUSiW6du0qXoR383UijXF1dTX53BBmbj7HfTfzNszfMG9paSn++OMP9OrV65a6xtpu5u7ujoiICGzduhVdunSBTqdDfHy8yXadP38egiCgd+/e6Nq1q8l07tw5lJaW/ul6iOhW58+fR0VFBZycnG75blVWVorfrccffxxBQUFYtmwZunTpggkTJmDbtm2oqqpq9rpjYmJQXl6Ohx9+GF5eXli4cCFOnz4t9l+4cAGCIOCVV165ZWyvvvoqAPC730bwGhgyOdLSoLy8HI8//jiUSiViYmLQs2dP2NjY4OTJk1i8eDHq6+v/dLmWlpaNtgt3cef+vcx7t9566y28+OKL+OSTT7B//37MmzcPsbGxOHr0KLp37476+nrIZDJ8/vnnjY6H17kQNU99fT2cnJyQlJTUaH/DdWwymQwfffQRjh49ir1792Lfvn2YPn063nrrLRw9erRZ38ERI0bg+++/F7/3W7duxZo1a5CQkIAZM2aI+7aXX34ZOp2u0WXczX+SqOUxwFCjDh48iN9++w0ff/wxRowYIbYXFhaacVT/j5OTE2xsbHDhwoVb+hprux0vLy94eXlh6dKlOHLkCIYNG4aEhASsWLECPXv2hCAIcHd3x8MPP3zH5fBpwkR3r2fPnjhw4ACGDRvW6H+gbubr6wtfX1+89tprSE5ORkhICD788EPMmDGjWd89BwcHTJs2DdOmTUNlZSVGjBiB6OhozJgxAw899BCA64+H8PPzu+Ny+L03L55CokY1HHG48YhHdXU1Nm3aZK4hmbC0tISfnx/27NmDS5cuie0XLlzA559//qfzG41G1NbWmrR5eXnBwsJCPDw9adIkWFpaYtmyZbcc+REEAb/99pv42c7O7q5OqxER8Mwzz6Curg7Lly+/pa+2thbl5eUArp9uvvm7N2jQIAAQv6cNz6xqmOfP3Pi9Ba4fSe3Vq5e4PCcnJ4wcORJvv/02fv7551vm/+WXX8Sf7ezsmrRuur94BIYa9de//hWdO3dGaGgo5s2bB5lMhn//+9/39RTOvYqOjsb+/fsxbNgwzJkzB3V1ddi4cSP69++PvLy8O86bmZmJ8PBwPP3003j44YdRW1uLf//737C0tERQUBCA6/9LXLFiBSIjI3Hx4kVMnDgRnTp1QmFhIXbv3o1Zs2bh5ZdfBgB4e3tjx44diIiIwNChQ9GxY0eMHz++pf8KiCTp8ccfx0svvYTY2Fjk5eXB398f1tbWOH/+PHbt2oV169Zh8uTJ2L59OzZt2oSnnnoKPXv2xJUrV/DOO+9AqVRi7NixAK6fAvf09MSOHTvw8MMPw8HBAf3790f//v0bXbenpydGjhwJb29vODg44MSJE/joo48QHh4u1sTHx2P48OHw8vLCzJkz8dBDD6GkpATZ2dn43//+h6+//hrA9TBlaWmJN998ExUVFVAoFHjiiSfg5OTU8n+JxNuoHyS3u426X79+jdYfPnxY8PX1FWxtbQVnZ2dh0aJFwr59+265bfB2t1GvXLnylmXiptsdb3cbtV6vv2VeNzc3ITQ01KQtIyNDeOSRRwS5XC707NlT2Lp1q/DPf/5TsLGxuc3fwnU//PCDMH36dKFnz56CjY2N4ODgIIwaNUo4cODALbX//e9/heHDhwt2dnaCnZ2d0LdvX0Gv1wsFBQViTWVlpfD8888L9vb2AgDeUk10g8b2PYIgCFu2bBG8vb0FW1tboVOnToKXl5ewaNEi4dKlS4IgCMLJkyeF5557TnB1dRUUCoXg5OQkjBs3Tjhx4oTJco4cOSJ4e3sLcrn8T2+pXrFihfDoo48K9vb2gq2trdC3b1/htddeE6qrq03qvv/+e2Hq1KmCRqMRrK2thb/85S/CuHHjhI8++sik7p133hEeeughwdLSkrdUtzK+C4nanYkTJ97xNkkiIpI+XgNDkvbHH3+YfD5//jw+++wzvliNiKid4xEYkrRu3brhxRdfxEMPPYQff/wRmzdvRlVVFU6dOoXevXube3hERNRCeBEvSdqYMWPwn//8BwaDAQqFAlqtFq+//jrDCxFRO8cjMERERCQ5vAaGiIiIJKdJAaZHjx6QyWS3THq9HgBw7do16PV6ODo6omPHjggKCkJJSYnJMoqKihAYGIgOHTrAyckJCxcuvOWBYgcPHsTgwYOhUCjQq1cvJCYm3ttWEhERUbvSpGtgjh8/jrq6OvHzN998gyeffBJPP/00AGDBggVITU0V3zQaHh6OSZMm4fDhwwCuv0E4MDAQGo0GR44cwc8//4ypU6fC2toar7/+OoDrj6oPDAzE7NmzkZSUhIyMDMyYMQPdunW77XspGlNfX49Lly6hU6dOfNwzkRkIgoArV67A2dkZFhbSONjL/QaR+d31vuNeHiLzj3/8Q+jZs6dQX18vlJeXC9bW1sKuXbvE/nPnzgkAhOzsbEEQBOGzzz4TLCwsBIPBINZs3rxZUCqVQlVVlSAIgrBo0aJbHqz27LPPCjqdrkljKy4uFgBw4sTJzFNxcXFzdzGtjvsNTpzazvRn+45m34VUXV2NDz74ABEREZDJZMjNzUVNTY3Jy6/69u0LV1dXZGdnw9fXF9nZ2fDy8oJarRZrdDod5syZg/z8fDzyyCPIzs6+5QVaOp0O8+fPv+N4qqqqTF6xLvz/1yYXFxdDqVQ2dzOJqJmMRiNcXFzQqVMncw/lrjWMlfsNIvO5231HswPMnj17UF5ejhdffBEAYDAYIJfLYW9vb1KnVqthMBjEmhvDS0N/Q9+daoxGI/7444/bvrk0NjYWy5Ytu6VdqVRyR0RkRlI6FdMwVu43iMzvz/YdzT4x/e677yIgIADOzs7NXcR9FRkZiYqKCnEqLi4295CIiIiohTTrCMyPP/6IAwcO4OOPPxbbNBoNqqurUV5ebnIUpqSkBBqNRqw5duyYybIa7lK6sebmO5dKSkqgVCpve/QFABQKBRQKRXM2h4iIiCSmWUdgtm3bBicnJwQGBopt3t7esLa2RkZGhthWUFCAoqIiaLVaAIBWq8WZM2dQWloq1qSnp0OpVMLT01OsuXEZDTUNyyAiIiJqcoCpr6/Htm3bEBoaCiur/3cAR6VSISwsDBEREfjiiy+Qm5uLadOmQavVwtfXFwDg7+8PT09PTJkyBV9//TX27duHpUuXQq/Xi0dPZs+ejR9++AGLFi3Ct99+i02bNmHnzp1YsGDBfdpkIiIikromn0I6cOAAioqKMH369Fv61qxZAwsLCwQFBaGqqgo6nQ6bNm0S+y0tLZGSkoI5c+ZAq9XCzs4OoaGhiImJEWvc3d2RmpqKBQsWYN26dejevTu2bt3apGfAEBERUfvWbt+FZDQaoVKpUFFRwbsJiMxAit9BKY6ZqL252++hNB6PSURERHQDBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSnGa9zLG96bEk1dxDeGBcfCPwz4uIJIL7jtbDfQfdjEdgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiKjFZWVlYfz48XB2doZMJsOePXtuqTl37hz+9re/QaVSwc7ODkOHDkVRUZHYf+3aNej1ejg6OqJjx44ICgpCSUmJyTKKiooQGBiIDh06wMnJCQsXLkRtbW1Lbx4RmQEDDBG1uKtXr2LgwIGIj49vtP/777/H8OHD0bdvXxw8eBCnT5/GK6+8AhsbG7FmwYIF2Lt3L3bt2oVDhw7h0qVLmDRpkthfV1eHwMBAVFdX48iRI9i+fTsSExMRFRXV4ttHRK3PytwDIKL2LyAgAAEBAbft/9e//oWxY8ciLi5ObOvZs6f4c0VFBd59910kJyfjiSeeAABs27YNHh4eOHr0KHx9fbF//36cPXsWBw4cgFqtxqBBg7B8+XIsXrwY0dHRkMvlLbeBRNTqeASGiMyqvr4eqampePjhh6HT6eDk5AQfHx+T00y5ubmoqamBn5+f2Na3b1+4uroiOzsbAJCdnQ0vLy+o1WqxRqfTwWg0Ij8/v9F1V1VVwWg0mkxEJA0MMERkVqWlpaisrMQbb7yBMWPGYP/+/XjqqacwadIkHDp0CABgMBggl8thb29vMq9arYbBYBBrbgwvDf0NfY2JjY2FSqUSJxcXl/u8dUTUUhhgiMis6uvrAQATJkzAggULMGjQICxZsgTjxo1DQkJCi647MjISFRUV4lRcXNyi6yOi+4cBhojMqkuXLrCysoKnp6dJu4eHh3gXkkajQXV1NcrLy01qSkpKoNFoxJqb70pq+NxQczOFQgGlUmkyEZE0MMAQkVnJ5XIMHToUBQUFJu3fffcd3NzcAADe3t6wtrZGRkaG2F9QUICioiJotVoAgFarxZkzZ1BaWirWpKenQ6lU3hKOiEj6eBcSEbW4yspKXLhwQfxcWFiIvLw8ODg4wNXVFQsXLsSzzz6LESNGYNSoUUhLS8PevXtx8OBBAIBKpUJYWBgiIiLg4OAApVKJuXPnQqvVwtfXFwDg7+8PT09PTJkyBXFxcTAYDFi6dCn0ej0UCoU5NpuIWhADDBG1uBMnTmDUqFHi54iICABAaGgoEhMT8dRTTyEhIQGxsbGYN28e+vTpg//+978YPny4OM+aNWtgYWGBoKAgVFVVQafTYdOmTWK/paUlUlJSMGfOHGi1WtjZ2SE0NBQxMTGtt6FE1GpkgiAI5h5ESzAajVCpVKioqPjT89o9lqS20qjo4huB5h4CtZKmfAfbiqaOmfuO1sN9x4Pjbr+HvAaGiIiIJIcBhoiIiCSHAYaIiIgkhwGGiIiIJIcBhoiIiCSHAYaIiIgkp8kB5qeffsILL7wAR0dH2NrawsvLCydOnBD7BUFAVFQUunXrBltbW/j5+eH8+fMmyygrK0NISAiUSiXs7e0RFhaGyspKk5rTp0/jscceg42NDVxcXBAXF9fMTSQiIqL2pkkB5vLlyxg2bBisra3x+eef4+zZs3jrrbfQuXNnsSYuLg7r169HQkICcnJyYGdnB51Oh2vXrok1ISEhyM/PR3p6OlJSUpCVlYVZs2aJ/UajEf7+/nBzc0Nubi5WrlyJ6OhobNmy5T5sMhEREUldk57E++abb8LFxQXbtm0T29zd3cWfBUHA2rVrsXTpUkyYMAEA8P7770OtVmPPnj0IDg7GuXPnkJaWhuPHj2PIkCEAgA0bNmDs2LFYtWoVnJ2dkZSUhOrqarz33nuQy+Xo168f8vLysHr1apOgQ0RERA+mJh2B+fTTTzFkyBA8/fTTcHJywiOPPIJ33nlH7C8sLITBYICfn5/YplKp4OPjg+zsbABAdnY27O3txfACAH5+frCwsEBOTo5YM2LECMjlcrFGp9OhoKAAly9fbnRsVVVVMBqNJhMRERG1T00KMD/88AM2b96M3r17Y9++fZgzZw7mzZuH7du3AwAMBgMAQK1Wm8ynVqvFPoPBACcnJ5N+KysrODg4mNQ0towb13Gz2NhYqFQqcXJxcWnKphEREZGENCnA1NfXY/DgwXj99dfxyCOPYNasWZg5cyYSEhJaanx3LTIyEhUVFeJUXFxs7iERERFRC2lSgOnWrRs8PT1N2jw8PFBUVAQA0Gg0AICSkhKTmpKSErFPo9GgtLTUpL+2thZlZWUmNY0t48Z13EyhUECpVJpMRERE1D41KcAMGzYMBQUFJm3fffcd3NzcAFy/oFej0SAjI0PsNxqNyMnJgVarBQBotVqUl5cjNzdXrMnMzER9fT18fHzEmqysLNTU1Ig16enp6NOnj8kdT0RERPRgalKAWbBgAY4ePYrXX38dFy5cQHJyMrZs2QK9Xg8AkMlkmD9/PlasWIFPP/0UZ86cwdSpU+Hs7IyJEycCuH7EZsyYMZg5cyaOHTuGw4cPIzw8HMHBwXB2dgYAPP/885DL5QgLC0N+fj527NiBdevWISIi4v5uPREREUlSk26jHjp0KHbv3o3IyEjExMTA3d0da9euRUhIiFizaNEiXL16FbNmzUJ5eTmGDx+OtLQ02NjYiDVJSUkIDw/H6NGjYWFhgaCgIKxfv17sV6lU2L9/P/R6Pby9vdGlSxdERUXxFmoiIiICAMgEQRDMPYiWYDQaoVKpUFFR8afXw/RYktpKo6KLbwSaewjUSpryHWwrmjpm7jtaD/cdD467/R7yXUhEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMETU4rKysjB+/Hg4OztDJpNhz549t62dPXs2ZDIZ1q5da9JeVlaGkJAQKJVK2NvbIywsDJWVlSY1p0+fxmOPPQYbGxu4uLggLi6uBbaGiNoCBhgianFXr17FwIEDER8ff8e63bt34+jRo3B2dr6lLyQkBPn5+UhPT0dKSgqysrIwa9Yssd9oNMLf3x9ubm7Izc3FypUrER0djS1bttz37SEi87My9wCIqP0LCAhAQEDAHWt++uknzJ07F/v27UNgYKBJ37lz55CWlobjx49jyJAhAIANGzZg7NixWLVqFZydnZGUlITq6mq89957kMvl6NevH/Ly8rB69WqToENE7QOPwBCR2dXX12PKlClYuHAh+vXrd0t/dnY27O3txfACAH5+frCwsEBOTo5YM2LECMjlcrFGp9OhoKAAly9fbnS9VVVVMBqNJhMRSQMDDBGZ3ZtvvgkrKyvMmzev0X6DwQAnJyeTNisrKzg4OMBgMIg1arXapKbhc0PNzWJjY6FSqcTJxcXlXjeFiFoJAwwRmVVubi7WrVuHxMREyGSyVl13ZGQkKioqxKm4uLhV109EzccAQ0Rm9eWXX6K0tBSurq6wsrKClZUVfvzxR/zzn/9Ejx49AAAajQalpaUm89XW1qKsrAwajUasKSkpMalp+NxQczOFQgGlUmkyEZE0MMAQkVlNmTIFp0+fRl5enjg5Oztj4cKF2LdvHwBAq9WivLwcubm54nyZmZmor6+Hj4+PWJOVlYWamhqxJj09HX369EHnzp1bd6OIqMXxLiQianGVlZW4cOGC+LmwsBB5eXlwcHCAq6srHB0dTeqtra2h0WjQp08fAICHhwfGjBmDmTNnIiEhATU1NQgPD0dwcLB4y/Xzzz+PZcuWISwsDIsXL8Y333yDdevWYc2aNa23oUTUahhgiKjFnThxAqNGjRI/R0REAABCQ0ORmJh4V8tISkpCeHg4Ro8eDQsLCwQFBWH9+vViv0qlwv79+6HX6+Ht7Y0uXbogKiqKt1ATtVMMMETU4kaOHAlBEO66/uLFi7e0OTg4IDk5+Y7zDRgwAF9++WVTh0dEEsRrYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIcpoUYKKjoyGTyUymvn37iv3Xrl2DXq+Ho6MjOnbsiKCgIJSUlJgso6ioCIGBgejQoQOcnJywcOFC1NbWmtQcPHgQgwcPhkKhQK9evZCYmNj8LSQiIqJ2p8lHYPr164eff/5ZnL766iuxb8GCBdi7dy927dqFQ4cO4dKlS5g0aZLYX1dXh8DAQFRXV+PIkSPYvn07EhMTERUVJdYUFhYiMDAQo0aNQl5eHubPn48ZM2Zg375997ipRERE1F5YNXkGKytoNJpb2isqKvDuu+8iOTkZTzzxBABg27Zt8PDwwNGjR+Hr64v9+/fj7NmzOHDgANRqNQYNGoTly5dj8eLFiI6OhlwuR0JCAtzd3fHWW28BADw8PPDVV19hzZo10Ol097i5RERE1B40+QjM+fPn4ezsjIceegghISEoKioCAOTm5qKmpgZ+fn5ibd++feHq6ors7GwAQHZ2Nry8vKBWq8UanU4Ho9GI/Px8sebGZTTUNCzjdqqqqmA0Gk0mIiIiap+aFGB8fHyQmJiItLQ0bN68GYWFhXjsscdw5coVGAwGyOVy2Nvbm8yjVqthMBgAAAaDwSS8NPQ39N2pxmg04o8//rjt2GJjY6FSqcTJxcWlKZtGREREEtKkU0gBAQHizwMGDICPjw/c3Nywc+dO2Nra3vfBNUVkZCQiIiLEz0ajkSGGiIionbqn26jt7e3x8MMP48KFC9BoNKiurkZ5eblJTUlJiXjNjEajueWupIbPf1ajVCrvGJIUCgWUSqXJRERERO3TPQWYyspKfP/99+jWrRu8vb1hbW2NjIwMsb+goABFRUXQarUAAK1WizNnzqC0tFSsSU9Ph1KphKenp1hz4zIaahqWQURERNSkAPPyyy/j0KFDuHjxIo4cOYKnnnoKlpaWeO6556BSqRAWFoaIiAh88cUXyM3NxbRp06DVauHr6wsA8Pf3h6enJ6ZMmYKvv/4a+/btw9KlS6HX66FQKAAAs2fPxg8//IBFixbh22+/xaZNm7Bz504sWLDg/m89ERERSVKTroH53//+h+eeew6//fYbunbtiuHDh+Po0aPo2rUrAGDNmjWwsLBAUFAQqqqqoNPpsGnTJnF+S0tLpKSkYM6cOdBqtbCzs0NoaChiYmLEGnd3d6SmpmLBggVYt24dunfvjq1bt/IWaiIiIhI1KcB8+OGHd+y3sbFBfHw84uPjb1vj5uaGzz777I7LGTlyJE6dOtWUoREREdEDhO9CIiIiIslhgCEiIiLJYYAhohaXlZWF8ePHw9nZGTKZDHv27BH7ampqsHjxYnh5ecHOzg7Ozs6YOnUqLl26ZLKMsrIyhISEQKlUwt7eHmFhYaisrDSpOX36NB577DHY2NjAxcUFcXFxrbF5RGQGDDBE1OKuXr2KgQMHNnp93O+//46TJ0/ilVdewcmTJ/Hxxx+joKAAf/vb30zqQkJCkJ+fj/T0dKSkpCArKwuzZs0S+41GI/z9/eHm5obc3FysXLkS0dHR2LJlS4tvHxG1via/zJGIqKkCAgJMnuR9I5VKhfT0dJO2jRs34tFHH0VRURFcXV1x7tw5pKWl4fjx4xgyZAgAYMOGDRg7dixWrVoFZ2dnJCUlobq6Gu+99x7kcjn69euHvLw8rF692iToEFH7wCMwRNTmVFRUQCaTie9Wy87Ohr29vRheAMDPzw8WFhbIyckRa0aMGAG5XC7W6HQ6FBQU4PLly42uhy+BJZIuBhgialOuXbuGxYsX47nnnhNfCWIwGODk5GRSZ2VlBQcHhya9LPZmfAkskXQxwBBRm1FTU4NnnnkGgiBg8+bNLb6+yMhIVFRUiFNxcXGLr5OI7g9eA0NEbUJDePnxxx+RmZlp8kJWjUZj8g41AKitrUVZWVmTXhZ7M4VCIb7GhIikhUdgiMjsGsLL+fPnceDAATg6Opr0a7ValJeXIzc3V2zLzMxEfX09fHx8xJqsrCzU1NSINenp6ejTpw86d+7cOhtCRK2GAYaIWlxlZSXy8vKQl5cHACgsLEReXh6KiopQU1ODyZMn48SJE0hKSkJdXR0MBgMMBgOqq6sBAB4eHhgzZgxmzpyJY8eO4fDhwwgPD0dwcDCcnZ0BAM8//zzkcjnCwsKQn5+PHTt2YN26dYiIiDDXZhNRC+IpJCJqcSdOnMCoUaPEzw2hIjQ0FNHR0fj0008BAIMGDTKZ74svvsDIkSMBAElJSQgPD8fo0aPFl8auX79erFWpVNi/fz/0ej28vb3RpUsXREVF8RZqonaKAYaIWtzIkSMhCMJt++/U18DBwQHJycl3rBkwYAC+/PLLJo+PiKSHp5CIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIcu4pwLzxxhuQyWSYP3++2Hbt2jXo9Xo4OjqiY8eOCAoKQklJicl8RUVFCAwMRIcOHeDk5ISFCxeitrbWpObgwYMYPHgwFAoFevXqhcTExHsZKhEREbUjzQ4wx48fx9tvv40BAwaYtC9YsAB79+7Frl27cOjQIVy6dAmTJk0S++vq6hAYGIjq6mocOXIE27dvR2JiIqKiosSawsJCBAYGYtSoUcjLy8P8+fMxY8YM7Nu3r7nDJSIionakWQGmsrISISEheOedd9C5c2exvaKiAu+++y5Wr16NJ554At7e3ti2bRuOHDmCo0ePAgD279+Ps2fP4oMPPsCgQYMQEBCA5cuXIz4+HtXV1QCAhIQEuLu746233oKHhwfCw8MxefJkrFmz5j5sMhEREUldswKMXq9HYGAg/Pz8TNpzc3NRU1Nj0t63b1+4uroiOzsbAJCdnQ0vLy+o1WqxRqfTwWg0Ij8/X6y5edk6nU5cRmOqqqpgNBpNJiJqG7KysjB+/Hg4OztDJpNhz549Jv2CICAqKgrdunWDra0t/Pz8cP78eZOasrIyhISEQKlUwt7eHmFhYaisrDSpOX36NB577DHY2NjAxcUFcXFxLb1pRGQmTQ4wH374IU6ePInY2Nhb+gwGA+RyOezt7U3a1Wo1DAaDWHNjeGnob+i7U43RaMQff/zR6LhiY2OhUqnEycXFpambRkQt5OrVqxg4cCDi4+Mb7Y+Li8P69euRkJCAnJwc2NnZQafT4dq1a2JNSEgI8vPzkZ6ejpSUFGRlZWHWrFliv9FohL+/P9zc3JCbm4uVK1ciOjoaW7ZsafHtI6LWZ9WU4uLiYvzjH/9Aeno6bGxsWmpMzRIZGYmIiAjxs9FoZIghaiMCAgIQEBDQaJ8gCFi7di2WLl2KCRMmAADef/99qNVq7NmzB8HBwTh37hzS0tJw/PhxDBkyBACwYcMGjB07FqtWrYKzszOSkpJQXV2N9957D3K5HP369UNeXh5Wr15tEnSIqH1o0hGY3NxclJaWYvDgwbCysoKVlRUOHTqE9evXw8rKCmq1GtXV1SgvLzeZr6SkBBqNBgCg0WhuuSup4fOf1SiVStja2jY6NoVCAaVSaTIRUdtXWFgIg8FgctpYpVLBx8fH5NSzvb29GF4AwM/PDxYWFsjJyRFrRowYAblcLtbodDoUFBTg8uXLja6bp56JpKtJAWb06NE4c+YM8vLyxGnIkCEICQkRf7a2tkZGRoY4T0FBAYqKiqDVagEAWq0WZ86cQWlpqViTnp4OpVIJT09PsebGZTTUNCyDiNqPhlPHjZ02vvG0spOTk0m/lZUVHBwcmnR6+mY89UwkXU06hdSpUyf079/fpM3Ozg6Ojo5ie1hYGCIiIuDg4AClUom5c+dCq9XC19cXAODv7w9PT09MmTIFcXFxMBgMWLp0KfR6PRQKBQBg9uzZ2LhxIxYtWoTp06cjMzMTO3fuRGpq6v3YZiIiADz1TCRlTQowd2PNmjWwsLBAUFAQqqqqoNPpsGnTJrHf0tISKSkpmDNnDrRaLezs7BAaGoqYmBixxt3dHampqViwYAHWrVuH7t27Y+vWrdDpdPd7uERkZg2njktKStCtWzexvaSkBIMGDRJrbjxqCwC1tbUoKytr0unpmykUCvE/TkQkLfccYA4ePGjy2cbGBvHx8be92wAA3Nzc8Nlnn91xuSNHjsSpU6fudXhE1Ma5u7tDo9EgIyNDDCxGoxE5OTmYM2cOgOunlcvLy5Gbmwtvb28AQGZmJurr6+Hj4yPW/Otf/0JNTQ2sra0BXD/13KdPH5PnVRFR+8B3IRFRi6usrBSvmwOuX7ibl5eHoqIi8XUkK1aswKeffoozZ85g6tSpcHZ2xsSJEwEAHh4eGDNmDGbOnIljx47h8OHDCA8PR3BwMJydnQEAzz//PORyOcLCwpCfn48dO3Zg3bp1JqeIiKj9uO+nkIiIbnbixAmMGjVK/NwQKkJDQ5GYmIhFixbh6tWrmDVrFsrLyzF8+HCkpaWZPK4hKSkJ4eHhGD16tHiaev369WK/SqXC/v37odfr4e3tjS5duiAqKoq3UBO1UwwwRNTiRo4cCUEQbtsvk8kQExNjci3czRwcHJCcnHzH9QwYMABffvlls8dJRNLBU0hEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEREQkOQwwREREJDkMMERERCQ5DDBEZHZ1dXV45ZVX4O7uDltbW/Ts2RPLly+HIAhijSAIiIqKQrdu3WBraws/Pz+cP3/eZDllZWUICQmBUqmEvb09wsLCUFlZ2dqbQ0StgAGGiMzuzTffxObNm7Fx40acO3cOb775JuLi4rBhwwaxJi4uDuvXr0dCQgJycnJgZ2cHnU6Ha9euiTUhISHIz89Heno6UlJSkJWVhVmzZpljk4iohVmZewBEREeOHMGECRMQGBgIAOjRowf+85//4NixYwCuH31Zu3Ytli5digkTJgAA3n//fajVauzZswfBwcE4d+4c0tLScPz4cQwZMgQAsGHDBowdOxarVq2Cs7OzeTaOiFoEj8AQkdn99a9/RUZGBr777jsAwNdff42vvvoKAQEBAIDCwkIYDAb4+fmJ86hUKvj4+CA7OxsAkJ2dDXt7ezG8AICfnx8sLCyQk5PT6HqrqqpgNBpNJiKSBh6BISKzW7JkCYxGI/r27QtLS0vU1dXhtddeQ0hICADAYDAAANRqtcl8arVa7DMYDHBycjLpt7KygoODg1hzs9jYWCxbtux+bw4RtQIegSEis9u5cyeSkpKQnJyMkydPYvv27Vi1ahW2b9/eouuNjIxERUWFOBUXF7fo+ojo/uERGCIyu4ULF2LJkiUIDg4GAHh5eeHHH39EbGwsQkNDodFoAAAlJSXo1q2bOF9JSQkGDRoEANBoNCgtLTVZbm1tLcrKysT5b6ZQKKBQKFpgi4iopfEIDBGZ3e+//w4LC9PdkaWlJerr6wEA7u7u0Gg0yMjIEPuNRiNycnKg1WoBAFqtFuXl5cjNzRVrMjMzUV9fDx8fn1bYCiJqTTwCQ0RmN378eLz22mtwdXVFv379cOrUKaxevRrTp08HAMhkMsyfPx8rVqxA79694e7ujldeeQXOzs6YOHEiAMDDwwNjxozBzJkzkZCQgJqaGoSHhyM4OJh3IBG1Q006ArN582YMGDAASqUSSqUSWq0Wn3/+udh/7do16PV6ODo6omPHjggKCkJJSYnJMoqKihAYGIgOHTrAyckJCxcuRG1trUnNwYMHMXjwYCgUCvTq1QuJiYnN30IiavM2bNiAyZMn4+9//zs8PDzw8ssv46WXXsLy5cvFmkWLFmHu3LmYNWsWhg4disrKSqSlpcHGxkasSUpKQt++fTF69GiMHTsWw4cPx5YtW8yxSUTUwmTCjY+6/BN79+6FpaUlevfuDUEQsH37dqxcuRKnTp1Cv379MGfOHKSmpiIxMREqlQrh4eGwsLDA4cOHAVx/2uagQYOg0WiwcuVK/Pzzz5g6dSpmzpyJ119/HcD12yX79++P2bNnY8aMGcjIyMD8+fORmpoKnU531xtmNBqhUqlQUVEBpVJ5x9oeS1Lverl0by6+EWjuIVAracp3sK1o6pi572g93Hc8OO72e9ikANMYBwcHrFy5EpMnT0bXrl2RnJyMyZMnAwC+/fZbeHh4IDs7G76+vvj8888xbtw4XLp0SbwdMiEhAYsXL8Yvv/wCuVyOxYsXIzU1Fd988424juDgYJSXlyMtLe2ux8UA0zZxJ/TgYICh+4n7jgfH3X4Pm30Rb11dHT788ENcvXoVWq0Wubm5qKmpMXnQVN++feHq6mryoCkvLy+TZznodDoYjUbk5+eLNTcuo6GmYRm3wwdSERERPTiaHGDOnDmDjh07QqFQYPbs2di9ezc8PT1hMBggl8thb29vUn/zg6YaexBVQ9+daoxGI/7444/bjis2NhYqlUqcXFxcmrppREREJBFNDjB9+vRBXl4ecnJyMGfOHISGhuLs2bMtMbYm4QOpiIiIHhxNvo1aLpejV69eAABvb28cP34c69atw7PPPovq6mqUl5ebHIUpKSkRHyKl0WjEl7Pd2N/Q1/DnzXculZSUQKlUwtbW9rbj4gOpiIiIHhz3/CC7+vp6VFVVwdvbG9bW1iYPmiooKEBRUZHJg6bOnDlj8rTM9PR0KJVKeHp6ijU3LqOhpmEZRERERE06AhMZGYmAgAC4urriypUrSE5OxsGDB7Fv3z6oVCqEhYUhIiICDg4OUCqVmDt3LrRaLXx9fQEA/v7+8PT0xJQpUxAXFweDwYClS5dCr9eLR09mz56NjRs3YtGiRZg+fToyMzOxc+dOpKbyan8iIiK6rkkBprS0FFOnTsXPP/8MlUqFAQMGYN++fXjyyScBAGvWrIGFhQWCgoJQVVUFnU6HTZs2ifNbWloiJSUFc+bMgVarhZ2dHUJDQxETEyPWuLu7IzU1FQsWLMC6devQvXt3bN26tUnPgCEiIqL27Z6fA9NW8TkwbROf5fDg4HNg6H7ivuPB0eLPgSEiIiIyFwYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYImoTfvrpJ7zwwgtwdHSEra0tvLy8cOLECbFfEARERUWhW7dusLW1hZ+fH86fP2+yjLKyMoSEhECpVMLe3h5hYWGorKxs7U0holbAAENEZnf58mUMGzYM1tbW+Pzzz3H27Fm89dZb6Ny5s1gTFxeH9evXIyEhATk5ObCzs4NOp8O1a9fEmpCQEOTn5yM9PR0pKSnIysrCrFmzzLFJRNTCrMw9ACKiN998Ey4uLti2bZvY5u7uLv4sCALWrl2LpUuXYsKECQCA999/H2q1Gnv27EFwcDDOnTuHtLQ0HD9+HEOGDAEAbNiwAWPHjsWqVavg7OzcuhtFRC2KR2CIyOw+/fRTDBkyBE8//TScnJzwyCOP4J133hH7CwsLYTAY4OfnJ7apVCr4+PggOzsbAJCdnQ17e3sxvACAn58fLCwskJOT0+h6q6qqYDQaTSYikgYGGCIyux9++AGbN29G7969sW/fPsyZMwfz5s3D9u3bAQAGgwEAoFarTeZTq9Vin8FggJOTk0m/lZUVHBwcxJqbxcbGQqVSiZOLi8v93jQiaiEMMERkdvX19Rg8eDBef/11PPLII5g1axZmzpyJhISEFl1vZGQkKioqxKm4uLhF10dE9w8DDBGZXbdu3eDp6WnS5uHhgaKiIgCARqMBAJSUlJjUlJSUiH0ajQalpaUm/bW1tSgrKxNrbqZQKKBUKk0mIpIGBhgiMrthw4ahoKDApO27776Dm5sbgOsX9Go0GmRkZIj9RqMROTk50Gq1AACtVovy8nLk5uaKNZmZmaivr4ePj08rbAURtSbehUREZrdgwQL89a9/xeuvv45nnnkGx44dw5YtW7BlyxYAgEwmw/z587FixQr07t0b7u7ueOWVV+Ds7IyJEycCuH7EZsyYMeKpp5qaGoSHhyM4OJh3IBG1QwwwRGR2Q4cOxe7duxEZGYmYmBi4u7tj7dq1CAkJEWsWLVqEq1evYtasWSgvL8fw4cORlpYGGxsbsSYpKQnh4eEYPXo0LCwsEBQUhPXr15tjk4iohTHAEFGbMG7cOIwbN+62/TKZDDExMYiJibltjYODA5KTk1tieETUxvAaGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSnCYFmNjYWAwdOhSdOnWCk5MTJk6ceMv7S65duwa9Xg9HR0d07NgRQUFBt7yAraioCIGBgejQoQOcnJywcOFC1NbWmtQcPHgQgwcPhkKhQK9evZCYmNi8LSQiIqJ2p0kB5tChQ9Dr9Th69CjS09NRU1MDf39/XL16VaxZsGAB9u7di127duHQoUO4dOkSJk2aJPbX1dUhMDAQ1dXVOHLkCLZv347ExERERUWJNYWFhQgMDMSoUaOQl5eH+fPnY8aMGdi3b9992GQiIiKSOpkgCEJzZ/7ll1/g5OSEQ4cOYcSIEaioqEDXrl2RnJyMyZMnAwC+/fZbeHh4IDs7G76+vvj8888xbtw4XLp0CWq1GgCQkJCAxYsX45dffoFcLsfixYuRmpqKb775RlxXcHAwysvLkZaWdldjMxqNUKlUqKiogFKpvGNtjyWpzfwboKa6+EaguYdAraQp38G2oqlj5r6j9XDf8eC42+/hPV0DU1FRAeD6+0cAIDc3FzU1NfDz8xNr+vbtC1dXV2RnZwMAsrOz4eXlJYYXANDpdDAajcjPzxdrblxGQ03DMhpTVVUFo9FoMhEREVH71OwAU19fj/nz52PYsGHo378/AMBgMEAul8Pe3t6kVq1Ww2AwiDU3hpeG/oa+O9UYjUb88ccfjY4nNjYWKpVKnFxcXJq7aURERNTGNTvA6PV6fPPNN/jwww/v53iaLTIyEhUVFeJUXFxs7iERERFRC7Fqzkzh4eFISUlBVlYWunfvLrZrNBpUV1ejvLzc5ChMSUkJNBqNWHPs2DGT5TXcpXRjzc13LpWUlECpVMLW1rbRMSkUCigUiuZsDhEREUlMk47ACIKA8PBw7N69G5mZmXB3dzfp9/b2hrW1NTIyMsS2goICFBUVQavVAgC0Wi3OnDmD0tJSsSY9PR1KpRKenp5izY3LaKhpWAYRERE92Jp0BEav1yM5ORmffPIJOnXqJF6zolKpYGtrC5VKhbCwMERERMDBwQFKpRJz586FVquFr68vAMDf3x+enp6YMmUK4uLiYDAYsHTpUuj1evEIyuzZs7Fx40YsWrQI06dPR2ZmJnbu3InUVF7xT0RERE08ArN582ZUVFRg5MiR6Natmzjt2LFDrFmzZg3GjRuHoKAgjBgxAhqNBh9//LHYb2lpiZSUFFhaWkKr1eKFF17A1KlTERMTI9a4u7sjNTUV6enpGDhwIN566y1s3boVOp3uPmwyERERSV2TjsDczSNjbGxsEB8fj/j4+NvWuLm54bPPPrvjckaOHIlTp041ZXhERET0gOC7kIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyGGCIiIhIchhgiKjNeeONNyCTyTB//nyx7dq1a9Dr9XB0dETHjh0RFBSEkpISk/mKiooQGBiIDh06wMnJCQsXLkRtbW0rj56IWgMDDBG1KcePH8fbb7+NAQMGmLQvWLAAe/fuxa5du3Do0CFcunQJkyZNEvvr6uoQGBiI6upqHDlyBNu3b0diYiKioqJaexOIqBUwwBBRm1FZWYmQkBC888476Ny5s9heUVGBd999F6tXr8YTTzwBb29vbNu2DUeOHMHRo0cBAPv378fZs2fxwQcfYNCgQQgICMDy5csRHx+P6upqc20SEbUQBhgiajP0ej0CAwPh5+dn0p6bm4uamhqT9r59+8LV1RXZ2dkAgOzsbHh5eUGtVos1Op0ORqMR+fn5ja6vqqoKRqPRZCIiabAy9wCIiADgww8/xMmTJ3H8+PFb+gwGA+RyOezt7U3a1Wo1DAaDWHNjeGnob+hrTGxsLJYtW3YfRk9ErY1HYIjI7IqLi/GPf/wDSUlJsLGxabX1RkZGoqKiQpyKi4tbbd1EdG8YYIjI7HJzc1FaWorBgwfDysoKVlZWOHToENavXw8rKyuo1WpUV1ejvLzcZL6SkhJoNBoAgEajueWupIbPDTU3UygUUCqVJhMRSQMDDBGZ3ejRo3HmzBnk5eWJ05AhQxASEiL+bG1tjYyMDHGegoICFBUVQavVAgC0Wi3OnDmD0tJSsSY9PR1KpRKenp6tvk1E1LJ4DQwRmV2nTp3Qv39/kzY7Ozs4OjqK7WFhYYiIiICDgwOUSiXmzp0LrVYLX19fAIC/vz88PT0xZcoUxMXFwWAwYOnSpdDr9VAoFK2+TUTUshhgiEgS1qxZAwsLCwQFBaGqqgo6nQ6bNm0S+y0tLZGSkoI5c+ZAq9XCzs4OoaGhiImJMeOoiailMMAQUZt08OBBk882NjaIj49HfHz8bedxc3PDZ5991sIjI6K2gNfAEBERkeQwwBAREZHkMMAQERGR5DDAEBERkeQwwBAREZHkMMAQERGR5DDAEBERkeQwwBAREZHk8EF21G70WJJq7iE8MC6+EWjuIRDRA45HYIiIiEhyGGCIiIhIchhgiIiISHIYYIiIiEhyeBEvERE90HgDQOu5nzcA8AgMERERSQ4DDBEREUkOAwwRERFJDgMMERERSQ4DDBEREUkOAwwRERFJTpMDTFZWFsaPHw9nZ2fIZDLs2bPHpF8QBERFRaFbt26wtbWFn58fzp8/b1JTVlaGkJAQKJVK2NvbIywsDJWVlSY1p0+fxmOPPQYbGxu4uLggLi6u6VtHRERE7VKTA8zVq1cxcOBAxMfHN9ofFxeH9evXIyEhATk5ObCzs4NOp8O1a9fEmpCQEOTn5yM9PR0pKSnIysrCrFmzxH6j0Qh/f3+4ubkhNzcXK1euRHR0NLZs2dKMTSQiIqL2pskPsgsICEBAQECjfYIgYO3atVi6dCkmTJgAAHj//fehVquxZ88eBAcH49y5c0hLS8Px48cxZMgQAMCGDRswduxYrFq1Cs7OzkhKSkJ1dTXee+89yOVy9OvXD3l5eVi9erVJ0CEiIqIH0329BqawsBAGgwF+fn5im0qlgo+PD7KzswEA2dnZsLe3F8MLAPj5+cHCwgI5OTlizYgRIyCXy8UanU6HgoICXL58udF1V1VVwWg0mkxERETUPt3XAGMwGAAAarXapF2tVot9BoMBTk5OJv1WVlZwcHAwqWlsGTeu42axsbFQqVTi5OLicu8bRERERG1Su7kLKTIyEhUVFeJUXFxs7iERERFRC7mvAUaj0QAASkpKTNpLSkrEPo1Gg9LSUpP+2tpalJWVmdQ0towb13EzhUIBpVJpMhEREVH7dF8DjLu7OzQaDTIyMsQ2o9GInJwcaLVaAIBWq0V5eTlyc3PFmszMTNTX18PHx0esycrKQk1NjViTnp6OPn36oHPnzvdzyERERCRBTQ4wlZWVyMvLQ15eHoDrF+7m5eWhqKgIMpkM8+fPx4oVK/Dpp5/izJkzmDp1KpydnTFx4kQAgIeHB8aMGYOZM2fi2LFjOHz4MMLDwxEcHAxnZ2cAwPPPPw+5XI6wsDDk5+djx44dWLduHSIiIu7bhhMREZF0Nfk26hMnTmDUqFHi54ZQERoaisTERCxatAhXr17FrFmzUF5ejuHDhyMtLQ02NjbiPElJSQgPD8fo0aNhYWGBoKAgrF+/XuxXqVTYv38/9Ho9vL290aVLF0RFRfEWaiIiIgLQjAAzcuRICIJw236ZTIaYmBjExMTctsbBwQHJycl3XM+AAQPw5ZdfNnV4RERE9ABoN3chEZF0xcbGYujQoejUqROcnJwwceJEFBQUmNRcu3YNer0ejo6O6NixI4KCgm652L+oqAiBgYHo0KEDnJycsHDhQtTW1rbmphBRK2GAISKzO3ToEPR6PY4ePYr09HTU1NTA398fV69eFWsWLFiAvXv3YteuXTh06BAuXbqESZMmif11dXUIDAxEdXU1jhw5gu3btyMxMRFRUVHm2CQiamFNPoVERHS/paWlmXxOTEyEk5MTcnNzMWLECFRUVODdd99FcnIynnjiCQDAtm3b4OHhgaNHj8LX1xf79+/H2bNnceDAAajVagwaNAjLly/H4sWLER0dbfJkbyKSPh6BIaI2p6KiAsD16+UAIDc3FzU1NSavKenbty9cXV1NXlPi5eVl8hRvnU4Ho9GI/Pz8RtfDV5AQSRcDDBG1KfX19Zg/fz6GDRuG/v37A7j+ChG5XA57e3uT2ptfU8JXkBA9OBhgiKhN0ev1+Oabb/Dhhx+2+Lr4ChIi6eI1METUZoSHhyMlJQVZWVno3r272K7RaFBdXY3y8nKTozA3v6bk2LFjJsu7m1eQKBSK+7wVRNQaeASGiMxOEASEh4dj9+7dyMzMhLu7u0m/t7c3rK2tTV5TUlBQgKKiIpPXlJw5c8bkXWvp6elQKpXw9PRsnQ0holbDIzBEZHZ6vR7Jycn45JNP0KlTJ/GaFZVKBVtbW6hUKoSFhSEiIgIODg5QKpWYO3cutFotfH19AQD+/v7w9PTElClTEBcXB4PBgKVLl0Kv1/MoC1E7xABDRGa3efNmANef9H2jbdu24cUXXwQArFmzRnz1SFVVFXQ6HTZt2iTWWlpaIiUlBXPmzIFWq4WdnR1CQ0Pv+FRwIpIuBhgiMrs7vZ6kgY2NDeLj4xEfH3/bGjc3N3z22Wf3c2hE1EbxGhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpKcNh1g4uPj0aNHD9jY2MDHxwfHjh0z95CISAK47yBq/9psgNmxYwciIiLw6quv4uTJkxg4cCB0Oh1KS0vNPTQiasO47yB6MLTZALN69WrMnDkT06ZNg6enJxISEtChQwe899575h4aEbVh3HcQPRiszD2AxlRXVyM3NxeRkZFim4WFBfz8/JCdnd3oPFVVVaiqqhI/V1RUAACMRuOfrq++6vd7HDHdrbv5fTQXf4+t525+jw01giC09HBETd133Mt+A+C/udbEfUf7cD/3HW0ywPz666+oq6uDWq02aVer1fj2228bnSc2NhbLli27pd3FxaVFxkjNo1pr7hHQ/dCU3+OVK1egUqlabCw3auq+g/sN6eC+o324n/uONhlgmiMyMhIRERHi5/r6epSVlcHR0REymcyMI2sZRqMRLi4uKC4uhlKpNPdwqJna8+9REARcuXIFzs7O5h7KbXG/QVLU3n+Pd7vvaJMBpkuXLrC0tERJSYlJe0lJCTQaTaPzKBQKKBQKkzZ7e/uWGmKboVQq2+U/4AdNe/09ttaRlwZN3Xdwv0FS1p5/j3ez72iTF/HK5XJ4e3sjIyNDbKuvr0dGRga0Wq0ZR0ZEbRn3HUQPjjZ5BAYAIiIiEBoaiiFDhuDRRx/F2rVrcfXqVUybNs3cQyOiNoz7DqIHQ5sNMM8++yx++eUXREVFwWAwYNCgQUhLS7vl4rwHlUKhwKuvvnrL4W+SFv4e7z/uO26P/97aB/4er5MJrXmPIxEREdF90CavgSEiIiK6EwYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGAmKj49Hjx49YGNjAx8fHxw7dszcQ6ImysrKwvjx4+Hs7AyZTIY9e/aYe0j0AOC+Q9q43zDFACMxO3bsQEREBF599VWcPHkSAwcOhE6nQ2lpqbmHRk1w9epVDBw4EPHx8eYeCj0guO+QPu43TPE5MBLj4+ODoUOHYuPGjQCuPybdxcUFc+fOxZIlS8w8OmoOmUyG3bt3Y+LEieYeCrVj3He0L9xv8AiMpFRXVyM3Nxd+fn5im4WFBfz8/JCdnW3GkRFRW8Z9B7VHDDAS8uuvv6Kuru6WR6Kr1WoYDAYzjYqI2jruO6g9YoAhIiIiyWGAkZAuXbrA0tISJSUlJu0lJSXQaDRmGhURtXXcd1B7xAAjIXK5HN7e3sjIyBDb6uvrkZGRAa1Wa8aREVFbxn0HtUdW5h4ANU1ERARCQ0MxZMgQPProo1i7di2uXr2KadOmmXto1ASVlZW4cOGC+LmwsBB5eXlwcHCAq6urGUdG7RX3HdLH/cZNBJKcDRs2CK6uroJcLhceffRR4ejRo+YeEjXRF198IQC4ZQoNDTX30Kgd475D2rjfMMXnwBAREZHk8BoYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpIcBhgiIiKSHAYYIiIikhwGGCIiIpKc/w/h/KDoR/ohKAAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Base-classifier">Base classifier<a class="anchor-link" href="#Base-classifier">&#182;</a></h2>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Random Forest classifier has been used for this problem as decisions such as this do not follow a strict sequence. For example, a person may have an old vehicle that has suffered damage in the past so they might want the car insurance but they are already paying a high premium for health insurance and therefore cannot afford the former. Or a certain policy sales channel might be very efficient at selling policies but it wouldn't matter if the customer doesn't have a valid driving license (or doesn't have an automobile).</p>
<p>In the first instance, we will test the performance of the base classifier (with default parameters) on the imbalanced dataset and discuss the results.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># checking performance of base classifier</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">RandomForestClassifier</span><span class="p">()</span>

<span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.88      0.95      0.91      1696
           1       0.49      0.29      0.37       304

    accuracy                           0.85      2000
   macro avg       0.69      0.62      0.64      2000
weighted avg       0.82      0.85      0.83      2000

</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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WcOnn37KwIEDAVi4cCGXXHIJjzzyCHFxcSxfvpyqqipeeOEFgoODOeOMM8jOzuaxxx5zSxwaQhUCERExBV+GC345IbG0tNTtqKys9DqWPXv24HA4SExMdJ2z2+0MGjSIzMxMADIzM4mMjHQlAwCJiYlYrVa2bNniajN48GCCg4NdbZKSksjNzeXQoUNexaSEQERExAvx8fHY7XbXkZaW5vU9HA4HADExMW7nY2JiXNccDgfR0dFu1wMDA4mKinJrc6x7/PI9GkpDBiIiYg6NmBh4VH8gPz8fm83mOh0SEuJrZCcFVQhERMQU6ucQ+HIA2Gw2t6MxCUFsbCwABQUFbucLCgpc12JjYyksLHS7XlNTQ1FRkVubY93jl+/RUEoIRERETrBu3boRGxvL2rVrXedKS0vZsmULCQkJACQkJFBcXExWVparzbp163A6nQwaNMjVZuPGjVRXV7vaZGRk0LNnT9q1a+dVTEoIRETEHAw/HF4oKysjOzub7OxsoG4iYXZ2Nnl5eVgsFm677Tbuu+8+3nzzTbZv384111xDXFwcY8eOBaB3796MGDGCSZMm8cknn/DRRx+RmprKhAkTiIuLA+DKK68kODiYiRMnsmPHDlasWMETTzzB9OnTvf7xaA6BiIiYwoneunjr1q0MHTrU9br+SzolJYWlS5dyxx13UF5ezuTJkykuLubCCy9kzZo1hIaGuvosX76c1NRUhg0bhtVqZfz48aSnp7uu2+123n//faZMmcKAAQPo0KEDs2fP9nrJIYDFMH57ZeWbb77Z4BteeumlXgfRWKWlpdjtdg593R1bhIod0jolxfVv7hBEmkyNUc163qCkpMRtop4/1X9XdH5mNtY2ob/d4TicRyrImzyvSWNtTg2qENSXL36LxWKhtrbWl3hERESaTit/HoEvGpQQOJ3Opo5DRESkSelph575VGf/5X7LIiIiJ7UTPKmwpfE6IaitreXee+/l1FNPpW3btnz77bcAzJo1i+eff97vAYqIiEjT8zohuP/++1m6dCnz58932zv5zDPP5LnnnvNrcCIiIv5j8cPRenmdECxbtoxnnnmG5ORkAgICXOf79evHzp07/RqciIiI32jIwCOvE4L9+/fTo0ePo847nU63nZJERESk5fA6IejTpw+bNm066vy///1vzj77bL8EJSIi4neqEHjk9U6Fs2fP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Hsf69euxWCwUFxcft43FYmHVqlUNvuecOXPo37+/T3F99913WCwWsrOzfbqPiDQtJQTSKl177bVYLBYsFgvBwcH06NGDefPmUVNT0+Tv/Z///Id77723QW0b8iUuInIi6OFG0mqNGDGCF198kcrKSt555x2mTJlCUFAQd91111Ftq6qqCA4O9sv7RkVF+eU+IiInkioE0mqFhIQQGxtLly5duOmmm0hMTOTNN98Efi7z33///cTFxdGzZ08A8vPzufzyy4mMjCQqKooxY8bw3Xffue5ZW1vL9OnTiYyMpH379txxxx38+nEgvx4yqKys5M477yQ+Pp6QkBB69OjB888/z3fffed6oE67du2wWCxce+21QN3jpdPS0ujWrRthYWH069ePf//7327v884773D66acTFhbG0KFD3eJsqDvvvJPTTz+dNm3a0L17d2bNmkV1dfVR7Z5++mni4+Np06YNl19+OSUlJW7Xn3vuOXr37k1oaCi9evXiqaee8joWEWleSgjENMLCwqiqqnK9Xrt2Lbm5uWRkZLB69Wqqq6tJSkoiIiKCTZs28dFHH9G2bVtGjBjh6vfoo4+ydOlSXnjhBT788EOKiopYuXKlx/e95ppr+Ne//kV6ejo5OTk8/fTTtG3blvj4eF5//XUAcnNzOXjwIE888QQAaWlpLFu2jCVLlrBjxw6mTZvGVVddxYYNG4C6xGXcuHGMHj2a7OxsbrjhBmbOnOn1zyQiIoKlS5fy1Vdf8cQTT/Dss8/y+OOPu7XZtWsXr776Km+99RZr1qzhs88+4+abb3ZdX758ObNnz+b+++8nJyeHBx54gFmzZvHSSy95HY+INCNDpBVKSUkxxowZYxiGYTidTiMjI8MICQkxbr/9dtf1mJgYo7Ky0tXnn//8p9GzZ0/D6XS6zlVWVhphYWHGe++9ZxiGYXTs2NGYP3++63p1dbXRqVMn13sZhmFcfPHFxq233moYhmHk5uYagJGRkXHMOD/44AMDMA4dOuQ6V1FRYbRp08bYvHmzW9uJEycaV1xxhWEYhnHXXXcZffr0cbt+5513HnWvXwOMlStXHvf6ww8/bAwYMMD1+p577jECAgKMffv2uc69++67htVqNQ4ePGgYhmH87ne/M15++WW3+9x7771GQkKCYRiGsWfPHgMwPvvss+O+r4g0P80hkFZr9erVtG3blurqapxOJ1deeSVz5sxxXe/bt6/bvIHPP/+cXbt2ERER4XafiooKdu/eTUlJCQcPHmTQoEGua4GBgQwcOPCoYYN62dnZBAQEcPHFFzc47l27dnHkyBH++Mc/up2vqqri7LPPBiAnJ8ctDoCEhIQGv0e9FStWkJ6ezu7duykrK6OmpgabzebWpnPnzpx66qlu7+N0OsnNzSUiIoLdu3czceJEJk2a5GpTU1OD3W73Oh4RaT5KCKTVGjp0KIsXLyY4OJi4uDgCA93/uIeHh7u9LisrY8CAASxfvvyoe51yyimNiiEsLMzrPmVlZQC8/fbbbl/EUDcvwl8yMzNJTk5m7ty5JCUlYbfbeeWVV3j00Ue9jvXZZ589KkEJCAjwW6wi0vSUEEirFR4eTo8ePRrc/ve//z0rVqwgOjr6qN+S63Xs2JEtW7YwePBgoO434aysLH7/+98fs33fvn1xOp1s2LCBxMTEo67XVyhqa2td5/r06UNISAh5eXnHrSz07t3bNUGy3scff/zbH/IXNm/eTJcuXfjHP/7hOrd3796j2uXl5XHgwAHi4uJc72O1WunZsycxMTHExcXx7bffkpyc7NX7i8jJRZMKRX6SnJxMhw4dGDNmDJs2bWLPnj2sX7+eW265hX379gFw66238uCDD7Jq1Sp27tzJzTff7HEPga5du5KSksL111/PqlWrXPd89dVXAejSpQsWi4XVq1fz/fffU1ZWRkREBLfffjvTpk3jpZdeYvfu3Wzbto2FCxe6JurdeOONfPPNN8yYMYPc3Fxefvllli5d6tXnPe2008jLy+OVV15h9+7dpKenH3OCZGhoKCkpKXz++eds2rSJW265hcsvv5zY2FgA5s6dS1paGunp6Xz99dds376dF198kccee8yreESkeSkhEPlJmzZt2LhxI507d2bcuHH07t2biRMnUlFR4aoY/P3vf+fqq68mJSWFhIQEIiIi+POf/+zxvosXL+ayyy7j5ptvplevXkyaNIny8nIATj31VObOncvMmTOJiYkhNTUVgHvvvZdZs2aRlpZG7969GTFiBG+//TbdunUD6sb1X3/9dVatWkW/fv1YsmQJDzzwgFef99JLL2XatGmkpqbSv39/Nm/ezKxZs45q16NHD8aNG8cll1zC8OHDOeuss9yWFd5www0899xzvPjii/Tt25eLL76YpUuXumIVkZbBYhxvNpSIiIiYhioEIiIiooRARERElBCIiIgISghEREQEJQQiIiKCEgIRERFBCYGIiIighEBERERQQiAiIiIoIRARERGUEIiIiAjw/wFx/qhiP+rnMQAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We see in the classification report that the values of precision, recall and f-score is close to 1 (which is good) for label 0 but very low for label 1 (label 1 = those who bought auto insurance policies). It is more clear in the confusion matrix. Our model was able to predict those who won't buy policies quite well but due to the imbalance, it was not able to predict the ones who bought auto insurance policies. It was more biased towards 0 labels as they were much higher in number in the training set.</p>
<p>This is where we see that the model is not performing as expected. In a business, there will be a certain tolerance towards misclassification of the negative labels (in this case 0) as positive (1). But misclassification of a 1 as 0 means rejecting a potential customer which is bad for the business. Often, the actual challenge in these problems is to predict the minority classes well. For example, in student admissions, out of thousands of applications, only a few will be selected. In this case, the selected students are the minority class.</p>
<p>A natural instinct to solve such problems would be to try and increase the accuracy of the model by tuning the hyperparameters. We will try it in the next section.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Hyperparameter-tuning-with-different-scoring-metrics">Hyperparameter tuning with different scoring metrics<a class="anchor-link" href="#Hyperparameter-tuning-with-different-scoring-metrics">&#182;</a></h2>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># defining the list of parameters and then using grid search cv</span>
<span class="c1"># to determine the best combination against a chosen scoring metric</span>

<span class="n">n_estimators</span> <span class="o">=</span> <span class="p">[</span><span class="mi">10</span><span class="p">,</span> <span class="mi">50</span><span class="p">,</span> <span class="mi">100</span><span class="p">,</span> <span class="mi">200</span><span class="p">,</span> <span class="mi">500</span><span class="p">]</span>
<span class="n">max_features</span> <span class="o">=</span> <span class="p">[</span><span class="kc">None</span><span class="p">,</span> <span class="s1">&#39;sqrt&#39;</span><span class="p">,</span> <span class="s1">&#39;log2&#39;</span><span class="p">]</span>
<span class="n">class_weight</span> <span class="o">=</span> <span class="p">[</span><span class="kc">None</span><span class="p">,</span> <span class="s1">&#39;balanced&#39;</span><span class="p">]</span>
<span class="n">n_jobs</span> <span class="o">=</span> <span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>

<span class="n">grid_rf</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;n_estimators&#39;</span><span class="p">:</span> <span class="n">n_estimators</span><span class="p">,</span>
           <span class="s1">&#39;max_features&#39;</span><span class="p">:</span> <span class="n">max_features</span><span class="p">,</span>
           <span class="s1">&#39;class_weight&#39;</span><span class="p">:</span> <span class="n">class_weight</span><span class="p">,</span>
           <span class="s1">&#39;n_jobs&#39;</span><span class="p">:</span> <span class="n">n_jobs</span><span class="p">}</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scoring-metric:-Accuracy">Scoring metric: Accuracy<a class="anchor-link" href="#Scoring-metric:-Accuracy">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">randomforest_gridsearch_acc</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(),</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">grid_rf</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;accuracy&#39;</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="n">randomforest_gridsearch_acc</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">randomforest_gridsearch_acc</span><span class="o">.</span><span class="n">best_estimator_</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.88      0.95      0.91      1696
           1       0.51      0.28      0.36       304

    accuracy                           0.85      2000
   macro avg       0.69      0.61      0.64      2000
weighted avg       0.82      0.85      0.83      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgQAAAGzCAYAAABQJQ/GAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjcuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/bCgiHAAAACXBIWXMAAA9hAAAPYQGoP6dpAABBoklEQVR4nO3de1yUdfr/8fcAAorMIBoghqZZKmVaWkQH05UVzW01bfu5UZGZbgaVWh76lqZWUuaWYSZlB7PV7bCtVlZupKWW5IGizJCyNEwF2hAQjOPcvz+IqVl1YpxBZO7X8/u4H+3c9+dzzzV8eTgX1+dwWwzDMAQAAEzNr7kDAAAAzY+EAAAAkBAAAAASAgAAIBICAAAgEgIAACASAgAAIBICAAAgEgIAACASAgAAICmguQPwhN1u14EDBxQaGiqLxdLc4QAA3GQYhg4fPqzo6Gj5+TXd36iVlZWqrq72+D6BgYEKDg5uVNuNGzfq0UcfVXZ2tg4ePKhVq1Zp5MiRTm1yc3M1ffp0bdiwQbW1tYqNjdXrr7+uzp07O+K+66679PLLL6uqqkqJiYl66qmnFBkZ6bhHfn6+Jk6cqA8++EBt27ZVcnKy0tLSFBDg3ld8i04IDhw4oJiYmOYOAwDgoX379un0009vkntXVlaqa5e2Kiiq8/heUVFR2rNnT6OSgoqKCvXp00c333yzRo0addT1b7/9VpdddpnGjRunOXPmyGq1aufOnU73njx5st5++2299tprstlsSk1N1ahRo/Txxx9Lkurq6jR8+HBFRUVp8+bNOnjwoG688Ua1atVK8+bNc+uzWVryw41KS0sVFham7z89Q9a2jH7AN119du/mDgFoMrWq0Ud6RyUlJbLZbE3yHmVlZbLZbPo++wxZQ0/8u6LssF1d+u1VaWmprFarW30tFstRFYIxY8aoVatWeumll47Zp7S0VKeddppWrlypa665RpK0a9cu9erVS1lZWbr44ov17rvv6k9/+pMOHDjgqBpkZGRo+vTp+vHHHxUYGNjoGFt0haBhmMDa1s+j/ycDp7IAS6vmDgFoOr/8SXoyhn3bhlrUNvTE38eu+r5lZWVO54OCghQUFOTevex2vf3225o2bZoSExP12WefqWvXrrrnnnscSUN2drZqamqUkJDg6NezZ0917tzZkRBkZWWpd+/eTkMIiYmJmjhxonbu3Knzzz+/0THxLQoAMIU6w+7xIUkxMTGy2WyOIy0tze1YioqKVF5erocfflhDhw7Ve++9p6uvvlqjRo3Shg0bJEkFBQUKDAxUWFiYU9/IyEgVFBQ42vw2GWi43nDNHS26QgAAQGPZZciuEx8lb+i7b98+pyEDd6sDUn2FQJJGjBihyZMnS5L69u2rzZs3KyMjQ1dcccUJx3miqBAAAOAGq9XqdJxIQtChQwcFBAQoNjbW6XyvXr2Un58vqX4CY3V1tUpKSpzaFBYWKioqytGmsLDwqOsN19xBQgAAMAW7F/7PWwIDA3XhhRcqLy/P6fzXX3+tLl26SJL69eunVq1aad26dY7reXl5ys/PV3x8vCQpPj5eO3bsUFFRkaNNZmamrFbrUcnG72HIAABgCnWGoToPFta527e8vFy7d+92vN6zZ49ycnIUHh6uzp07a+rUqfp//+//acCAARo0aJDWrl2rt956Sx9++KEkyWazady4cZoyZYrCw8NltVp1++23Kz4+XhdffLEkaciQIYqNjdUNN9yg+fPnq6CgQPfdd59SUlLcrlyQEAAA0AS2b9+uQYMGOV5PmTJFkpScnKxly5bp6quvVkZGhtLS0nTHHXeoR48eev3113XZZZc5+jz++OPy8/PT6NGjnTYmauDv7681a9Zo4sSJio+PV0hIiJKTkzV37ly3423R+xA0rC099HU3lh3CZyVG923uEIAmU2vU6EO9cUJr+xvLsQ/BrmjP9yHoeaBJY21OVAgAAKZgl6E6L6wy8FX8WQ0AAKgQAADMwVv7EPgqEgIAgCmc7FUGLQ1DBgAAgAoBAMAc7L8cnvT3ZSQEAABTqPNwlYEnfVsCEgIAgCnUGfWHJ/19GXMIAAAAFQIAgDkwh8A1EgIAgCnYZVGdLB7192UMGQAAACoEAABzsBv1hyf9fRkJAQDAFOo8HDLwpG9LwJABAACgQgAAMAcqBK6REAAATMFuWGQ3PFhl4EHfloAhAwAAQIUAAGAODBm4RkIAADCFOvmpzoPCeJ0XYzkVkRAAAEzB8HAOgcEcAgAA4OuoEAAATIE5BK6REAAATKHO8FOd4cEcAh/fupghAwAAQIUAAGAOdllk9+DvYLt8u0RAQgAAMAXmELjGkAEAAKBCAAAwB88nFTJkAABAi1c/h8CDhxsxZAAAAHwdFQIAgCnYPXyWAasMAADwAcwhcI2EAABgCnb5sQ+BC8whAAAAVAgAAOZQZ1hU58EjjD3p2xKQEAAATKHOw0mFdQwZAAAAd23cuFFXXXWVoqOjZbFYtHr16uO2vfXWW2WxWLRw4UKn88XFxUpKSpLValVYWJjGjRun8vJypzZffPGFLr/8cgUHBysmJkbz588/oXhJCAAApmA3/Dw+3FFRUaE+ffpo8eLFLtutWrVKn3zyiaKjo4+6lpSUpJ07dyozM1Nr1qzRxo0bNWHCBMf1srIyDRkyRF26dFF2drYeffRRzZ49W88884xbsUoMGQAATOJkDxkMGzZMw4YNc9lm//79uv322/Wf//xHw4cPd7qWm5urtWvXatu2berfv78kadGiRbryyiu1YMECRUdHa8WKFaqurtbzzz+vwMBAnXPOOcrJydFjjz3mlDg0BhUCAACagd1u1w033KCpU6fqnHPOOep6VlaWwsLCHMmAJCUkJMjPz09btmxxtBkwYIACAwMdbRITE5WXl6dDhw65FQ8VAgCAKdjl2UoB+y//LSsrczofFBSkoKAgt+/3yCOPKCAgQHfccccxrxcUFCgiIsLpXEBAgMLDw1VQUOBo07VrV6c2kZGRjmvt2rVrdDxUCAAAptCwMZEnhyTFxMTIZrM5jrS0NLdjyc7O1hNPPKFly5bJYjk1ljNSIQAAwA379u2T1Wp1vD6R6sCmTZtUVFSkzp07O87V1dXprrvu0sKFC7V3715FRUWpqKjIqV9tba2Ki4sVFRUlSYqKilJhYaFTm4bXDW0ai4QAAGAKnj/LoL6v1Wp1SghOxA033KCEhASnc4mJibrhhhs0duxYSVJ8fLxKSkqUnZ2tfv36SZLWr18vu92uuLg4R5t7771XNTU1atWqlSQpMzNTPXr0cGu4QCIhAACYhF0W2eXJHAL3+paXl2v37t2O13v27FFOTo7Cw8PVuXNntW/f3ql9q1atFBUVpR49ekiSevXqpaFDh2r8+PHKyMhQTU2NUlNTNWbMGMcSxeuuu05z5szRuHHjNH36dH355Zd64okn9Pjjj7v9+UgIAACm4K0KQWNt375dgwYNcryeMmWKJCk5OVnLli1r1D1WrFih1NRUDR48WH5+fho9erTS09Md1202m9577z2lpKSoX79+6tChg2bNmuX2kkOJhAAAgCYxcOBAGW48Mnnv3r1HnQsPD9fKlStd9jvvvPO0adMmd8M7CgkBAMAUPN+YyLcX5pEQAABMwW5YZPdkHwIff9qhb6c7AACgUagQAABMwe7hkIHdx/+GJiEAAJjCiTyx8H/7+zLf/nQAAKBRqBAAAEyhThbVebAxkSd9WwISAgCAKTBk4JpvfzoAANAoVAgAAKZQJ8/K/nXeC+WUREIAADAFhgxcIyEAAJjCyX64UUvj258OAAA0ChUCAIApGLLI7sEcAoNlhwAAtHwMGbjm258OAAA0ChUCAIAp8Phj10gIAACmUOfh0w496dsS+PanAwAAjUKFAABgCgwZuEZCAAAwBbv8ZPegMO5J35bAtz8dAABoFCoEAABTqDMsqvOg7O9J35aAhAAAYArMIXCNhAAAYAqGh087NNipEAAA+DoqBAAAU6iTRXUePKDIk74tAQkBAMAU7IZn8wDshheDOQUxZAAAAKgQmM2OT0L02lMR+mZHGxUXttL9z+3RJcNKndrkfxOk5x6M1heftFVdrdTl7CrNXLpHEafXSJLe+Ud7fbCqnXbvaK0j5f56PXeH2trqjvl+1VUW3Tn8bH33VWs99V6ezjz35yb/jMDv8fMzdP1dBRo8ukTtTqvRT4WtlPlquFYujJBkkX+AoZumH9SFfzisjl2qVVHmp882heq5eR1VXNiqucPHCbJ7OKnQk74twSnx6RYvXqwzzjhDwcHBiouL09atW5s7JJ9VecRP3c75Wanzfjjm9QN7AzVl5FmK6V6pR/+1Wxnr8nTdpAIFBv9aK6v82U/9B5ZpzO2Fv/t+zz0YrfZRNV6LH/CGa1OK9Kfkn7T43k4af0VPPfdQR/3ltiKNGPdfSVJQa7u69/5ZKxdGKiXxLM295QydfmaV5izb08yRwxN2WTw+fFmzVwheeeUVTZkyRRkZGYqLi9PChQuVmJiovLw8RURENHd4PufCPxzWhX84fNzryx7uqIv+UKZbZh50nIs+o9qpzajxP0qSPt/c1uV7bVsfquwNoZr57B5tW2/1IGrAu2L7VyjrPzZtXVf/e1n4Q6AGjSxRj75HJElHDvvrnjFnOvVZfG8nLXr3G53WqVo/7g886TEDTa3ZKwSPPfaYxo8fr7Fjxyo2NlYZGRlq06aNnn/++eYOzXTsdmnrOqs6davS//21m67tfY7uGH6WNr9rc/teh34M0MKpMZq26HsFtfbxmThocb7aHqK+lx1Wp25VkqRusT/rnIsqXCauIdY62e1SRan/yQoTXtawU6Enhy9r1oSgurpa2dnZSkhIcJzz8/NTQkKCsrKymjEycyr5b4B+rvDXK09GqP+gw0r753e6dGip5t5yhr7ICmn0fQxDWjCps4bf8JPO7sOcAZx6XnkyQhveCNOzG3fp7e8/1+L3vtaqpR30wap2x2zfKsiucfce1Ierw3SknISgpWqYQ+DJ4cuadcjgv//9r+rq6hQZGel0PjIyUrt27TqqfVVVlaqqqhyvy8rKmjxGMzHs9f+NTyzTqAn1wwJnnvuzvtoeoreXd9B58RWNus8bz3XQz+V++n+NmGMANIcBfy7RH0aV6OGUzvo+L1hnnvOzbp1zQD8VttL7r4U7tfUPMHTv099LFmnRjNObKWKg6TX7HAJ3pKWlac6cOc0dhs+yhtfJP8BQl7Mrnc7HnFWpnVsbXyHI+ThUudkh+tMZfZzOpw47W38YdUhTn8j3SrzAiRo/8+AvVYL6isDeXa0VcXqNxtxe5JQQ1CcDexXZqVrTrj2T6kALZ5eHzzJgUmHT6dChg/z9/VVY6PyXZGFhoaKioo5qf88992jKlCmO12VlZYqJiWnyOM2iVaChs/sc0Q/fBjmd3/9dkGPJYWPc9sAPumn6r/9w/lTQSv933Zn6v4y96nn+Ea/FC5yooGC7oyLWwF4nWSy/zndpSAY6da3WtGvO1OFDLervJxyD4eFKAYOEoOkEBgaqX79+WrdunUaOHClJstvtWrdunVJTU49qHxQUpKCgoKPOo/F+rvDTgT2//gwL9gXq2y9bKzSsVhGn1+gvtxVp3q1ddO7F5epzSbm2f2DVJ5k2Pfqv3Y4+xUUBOlTUSgf21M+03rMrWG1C7DqtU7Ws7ep+SR5+TSCCQ+r/5Y3uUq3TolmCiOb3SaZVY+4oUtH+wPohg3N/1qi//aj3Xq6vDvgHGJq5dK+69/5Zs27sKj9/Q+1Oq//dPVzir9oa3x5L9lU87dC1Zv+tnjJlipYuXaoXX3xRubm5mjhxoioqKjR27NjmDs0nff15G902pIduG9JDkvT07E66bUgPLV/QUZJ06bBS3fHwD3rtqUjdOrin1q5sr5lL9+jcuF/nD7y9vINuG9JDC6d2liTdffVZum1ID33ynvurEYDm8NR9nfTR2zalpv2gpRt2afysA3rnpfZ6cX59ZbJDVI3iE8t0WnSNlrz/tV7+/CvHEdufKhcaZ+PGjbrqqqsUHR0ti8Wi1atXO67V1NRo+vTp6t27t0JCQhQdHa0bb7xRBw4ccLpHcXGxkpKSZLVaFRYWpnHjxqm8vNypzRdffKHLL79cwcHBiomJ0fz5808oXothGM2+JuzJJ5/Uo48+qoKCAvXt21fp6emKi4v73X5lZWWy2Ww69HU3WUObPbcBmkRidN/mDgFoMrVGjT7UGyotLZXV2jT7lTR8V1ydOVatQk58D4maimqt+uMLjY713Xff1ccff6x+/fpp1KhRWrVqlaMaXlpaqmuuuUbjx49Xnz59dOjQId15552qq6vT9u3bHfcYNmyYDh48qKefflo1NTUaO3asLrzwQq1cudLx2c4++2wlJCTonnvu0Y4dO3TzzTdr4cKFmjBhgluf75RICE4UCQHMgIQAvuxkJgQj3rvZ44TgjSHPn1CsFovFKSE4lm3btumiiy7S999/r86dOys3N1exsbHatm2b+vfvL0lau3atrrzySv3www+Kjo7WkiVLdO+996qgoECBgfWfbcaMGVq9evUxV+u5wrcoAABuKCsrczp+uxzeE6WlpbJYLAoLC5MkZWVlKSwszJEMSFJCQoL8/Py0ZcsWR5sBAwY4kgFJjt1+Dx065Nb7kxAAAEzBW88yiImJkc1mcxxpaWkex1ZZWanp06frr3/9q6P6UFBQcNQW/gEBAQoPD1dBQYGjzbH28mm45g7W0QAATMFbqwz27dvnNGTg6eq3mpoaXXvttTIMQ0uWLPHoXp4gIQAAwA1Wq9Vr8x0akoHvv/9e69evd7pvVFSUioqKnNrX1taquLjYsVdPVFTUMffyabjmDoYMAACm0FAh8OTwpoZk4JtvvtH777+v9u3bO12Pj49XSUmJsrOzHefWr18vu93uWIkXHx+vjRs3qqbm1z1eMjMz1aNHD7Vrd+xncxwPCQEAwBROdkJQXl6unJwc5eTkSJL27NmjnJwc5efnq6amRtdcc422b9+uFStWqK6uTgUFBSooKFB1df0j53v16qWhQ4dq/Pjx2rp1qz7++GOlpqZqzJgxio6OliRdd911CgwM1Lhx47Rz50698soreuKJJ5x29W0shgwAAGgC27dv16BBgxyvG76kk5OTNXv2bL355puSpL59+zr1++CDDzRw4EBJ0ooVK5SamqrBgwfLz89Po0ePVnp6uqOtzWbTe++9p5SUFPXr108dOnTQrFmz3N6DQCIhAACYxMneunjgwIFytdVPY7YBCg8Pd2xCdDznnXeeNm3a5FZsx0JCAAAwBUOePbGwxe7i10gkBAAAU+DhRq4xqRAAAFAhAACYAxUC10gIAACmQELgGkMGAACACgEAwByoELhGQgAAMAXDsMjw4Evdk74tAUMGAACACgEAwBzssni0MZEnfVsCEgIAgCkwh8A1hgwAAAAVAgCAOTCp0DUSAgCAKTBk4BoJAQDAFKgQuMYcAgAAQIUAAGAOhodDBr5eISAhAACYgiHJMDzr78sYMgAAAFQIAADmYJdFFnYqPC4SAgCAKbDKwDWGDAAAABUCAIA52A2LLGxMdFwkBAAAUzAMD1cZ+PgyA4YMAAAAFQIAgDkwqdA1EgIAgCmQELhGQgAAMAUmFbrGHAIAAECFAABgDqwycI2EAABgCvUJgSdzCLwYzCmIIQMAAECFAABgDqwycI2EAABgCsYvhyf9fRlDBgAAgAoBAMAcGDJwjYQAAGAOjBm4xJABAMAcfqkQnOghNysEGzdu1FVXXaXo6GhZLBatXr3aORzD0KxZs9SxY0e1bt1aCQkJ+uabb5zaFBcXKykpSVarVWFhYRo3bpzKy8ud2nzxxRe6/PLLFRwcrJiYGM2fP/+EfjwkBAAANIGKigr16dNHixcvPub1+fPnKz09XRkZGdqyZYtCQkKUmJioyspKR5ukpCTt3LlTmZmZWrNmjTZu3KgJEyY4rpeVlWnIkCHq0qWLsrOz9eijj2r27Nl65pln3I6XIQMAgCmc7J0Khw0bpmHDhh3nXoYWLlyo++67TyNGjJAkLV++XJGRkVq9erXGjBmj3NxcrV27Vtu2bVP//v0lSYsWLdKVV16pBQsWKDo6WitWrFB1dbWef/55BQYG6pxzzlFOTo4ee+wxp8ShMagQAABMwZPhgt9OSCwrK3M6qqqq3I5lz549KigoUEJCguOczWZTXFycsrKyJElZWVkKCwtzJAOSlJCQID8/P23ZssXRZsCAAQoMDHS0SUxMVF5eng4dOuRWTCQEAAC4ISYmRjabzXGkpaW5fY+CggJJUmRkpNP5yMhIx7WCggJFREQ4XQ8ICFB4eLhTm2Pd47fv0VgMGQAAzOEEJgYe1V/Svn37ZLVaHaeDgoI8jeyUQIUAAGAKDXMIPDkkyWq1Oh0nkhBERUVJkgoLC53OFxYWOq5FRUWpqKjI6Xptba2Ki4ud2hzrHr99j8YiIQAA4CTr2rWroqKitG7dOse5srIybdmyRfHx8ZKk+Ph4lZSUKDs729Fm/fr1stvtiouLc7TZuHGjampqHG0yMzPVo0cPtWvXzq2YSAgAAOZgeOFwQ3l5uXJycpSTkyOpfiJhTk6O8vPzZbFYNGnSJD344IN68803tWPHDt14442Kjo7WyJEjJUm9evXS0KFDNX78eG3dulUff/yxUlNTNWbMGEVHR0uSrrvuOgUGBmrcuHHauXOnXnnlFT3xxBOaMmWK2z+eRs0hePPNNxt9wz//+c9uBwEAQFM72VsXb9++XYMGDXK8bviSTk5O1rJlyzRt2jRVVFRowoQJKikp0WWXXaa1a9cqODjY0WfFihVKTU3V4MGD5efnp9GjRys9Pd1x3Waz6b333lNKSor69eunDh06aNasWW4vOZQki2H8/spKP7/GFRIsFovq6urcDuJElZWVyWaz6dDX3WQNpdgB35QY3be5QwCaTK1Row/1hkpLS50m6nlTw3dF52dmya9N8O93OA77kUrlT5jbpLE2p0ZVCOx2e1PHAQBA0/Px5xF4wqNlh5WVlU6lDQAATlU87dA1t+vsdXV1euCBB9SpUye1bdtW3333nSRp5syZeu6557weIAAAXnGSJxW2NG4nBA899JCWLVum+fPnO22VeO655+rZZ5/1anAAAODkcDshWL58uZ555hklJSXJ39/fcb5Pnz7atWuXV4MDAMB7LF44fJfbcwj279+v7t27H3Xebrc7bYwAAMApxdOyP0MGzmJjY7Vp06ajzv/rX//S+eef75WgAADAyeV2hWDWrFlKTk7W/v37Zbfb9e9//1t5eXlavny51qxZ0xQxAgDgOSoELrldIRgxYoTeeustvf/++woJCdGsWbOUm5urt956S3/84x+bIkYAADzX8LRDTw4fdkL7EFx++eXKzMz0diwAAKCZnPDGRNu3b1dubq6k+nkF/fr181pQAAB4228fYXyi/X2Z2wnBDz/8oL/+9a/6+OOPFRYWJkkqKSnRJZdcopdfflmnn366t2MEAMBzzCFwye05BLfccotqamqUm5ur4uJiFRcXKzc3V3a7XbfccktTxAgAAJqY2xWCDRs2aPPm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tDR17dpVrVu3Vp8+ffSvf/3L6X3eeecdnX322WrdurUGDRrkFGdjTZ8+XWeffbbatGmjbt26aebMmaqpqTmq3dNPP62YmBi1adNG1157rUpLS52uP/vss+rVq5eCg4PVs2dPPfXUU27HAqB5kRDANFq3bq3q6mrH63Xr1ikvL0+ZmZlas2aNampqlJiYqNDQUG3atEkff/yx2rZtq6FDhzr6/f3vf9eyZcv0/PPP66OPPlJxcbFWrVrl8n1vvPFG/fOf/1R6erpyc3P19NNPq23btoqJidHrr78uScrLy9PBgwf1xBNPSJLS0tK0fPlyZWRkaOfOnZo8ebKuv/56bdiwQVJ94jJq1ChdddVVysnJ0S233KIZM2a4/TMJDQ3VsmXL9NVXX+mJJ57Q0qVL9fjjjzu12b17t1599VW99dZbWrt2rT777DPddtttjusrVqzQrFmz9NBDDyk3N1fz5s3TzJkz9eKLL7odD4BmZAA+KDk52RgxYoRhGIZht9uNzMxMIygoyLj77rsd1yMjI42qqipHn5deesno0aOHYbfbHeeqqqqM1q1bG//5z38MwzCMjh07GvPnz3dcr6mpMU4//XTHexmGYVxxxRXGnXfeaRiGYeTl5RmSjMzMzGPG+cEHHxiSjEOHDjnOVVZWGm3atDE2b97s1HbcuHHGX//6V8MwDOOee+4xYmNjna5Pnz79qHv9L0nGqlWrjnv90UcfNfr16+d4ff/99xv+/v7GDz/84Dj37rvvGn5+fsbBgwcNwzCMM88801i5cqXTfR544AEjPj7eMAzD2LNnjyHJ+Oyzz477vgCaH3MI4LPWrFmjtm3bqqamRna7Xdddd51mz57tuN67d2+neQOff/65du/erdDQUKf7VFZW6ttvv1VpaakOHjyouLg4x7WAgAD179//qGGDBjk5OfL399cVV1zR6Lh3796tI0eO6I9//KPT+erqap1//vmSpNzcXKc4JCk+Pr7R79HglVdeUXp6ur799luVl5ertrZWVqvVqU3nzp3VqVMnp/ex2+3Ky8tTaGiovv32W40bN07jx493tKmtrZXNZnM7HgDNh4QAPmvQoEFasmSJAgMDFR0drYAA51/3kJAQp9fl5eXq16+fVqxYcdS9TjvttBOKoXXr1m73KS8vlyS9/fbbTl/EUv28CG/JyspSUlKS5syZo8TERNlsNr388sv6+9//7nasS5cuPSpB8ff391qsAJoeCQF8VkhIiLp3797o9hdccIFeeeUVRUREHPVXcoOOHTtqy5YtGjBggKT6v4Szs7N1wQUXHLN97969ZbfbtWHDBiUkJBx1vaFCUVdX5zgXGxuroKAg5efnH7ey0KtXL8cEyQaffPLJ73/I39i8ebO6dOmie++913Hu+++/P6pdfn6+Dhw4oOjoaMf7+Pn5qUePHoqMjFR0dLS+++47JSUlufX+AE4tTCoEfpGUlKQOHTpoxIgR2rRpk/bs2aMPP/xQd9xxh3744QdJ0p133qmHH35Yq1ev1q5du3Tbbbe53EPgjDPOUHJysm6++WatXr3acc9XX31VktSlSxdZLBatWbNGP/74o8rLyxUaGqq7775bkydP1osvvqhvv/1Wn376qRYtWuSYqHfrrbfqm2++0dSpU5WXl6eVK1dq2bJlbn3es846S/n5+Xr55Zf17bffKj09/ZgTJIODg5WcnKzPP/9cmzZt0h133KFrr71WUVFRkqQ5c+YoLS1N6enp+vrrr7Vjxw698MILeuyxx9yKB0DzIiEAftGmTRtt3LhRnTt31qhRo9SrVy+NGzdOlZWVjorBXXfdpRtuuEHJycmKj49XaGiorr76apf3XbJkia655hrddttt6tmzp8aPH6+KigpJUqdOnTRnzhzNmDFDkZGRSk1NlSQ98MADmjlzptLS0tSrVy8NHTpUb7/9trp27Sqpflz/9ddf1+rVq9WnTx9lZGRo3rx5bn3eP//5z5o8ebJSU1PVt29fbd68WTNnzjyqXffu3TVq1ChdeeWVGjJkiM477zynZYW33HKLnn32Wb3wwgvq3bu3rrjiCi1btswRK4CWwWIcbzYUAAAwDSoEAACAhAAAAJAQAAAAkRAAAACREAAAAJEQAAAAkRAAAACREAAAAJEQAAAAkRAAAACREAAAAJEQAAAASf8fiY9U30D5jTsAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We find almost no difference in the results between the base classifier and classifier tuned for accuracy although the value of which is quite high; 85%, which should be considered quite good. But no, the reason for the high accuracy value is the higher number of 0 labels that were correctly predicted.</p>
<p>This revelation changes our goal. Now we are not looking to increase the overall accuracy of the model but trying to reduce the misclassification of the minority class (number of 1s predicted as 0). To do this, we have to change our scoring metric for hyperparameter tuning. We can use precision or f-score (combination of precision and recall) to do so. There is another scoring parameter called ROC AUC which gives the area under the ROC curve which is a plot of true positives vs false positives. For more on scoring parameters, refer to the scikit learn page <a href="https://scikit-learn.org/stable/modules/model_evaluation.html#scoring-parameter">here.</a></p>
<p>We will try a couple of these scoring parameters in the next sections. The method will remain the same, only the results need to be checked for each scoring metric.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scoring-metric:-F-score">Scoring metric: F-score<a class="anchor-link" href="#Scoring-metric:-F-score">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">randomforest_gridsearch_f1</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(),</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">grid_rf</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;f1_weighted&#39;</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="n">randomforest_gridsearch_f1</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">randomforest_gridsearch_f1</span><span class="o">.</span><span class="n">best_estimator_</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.91      0.91      0.91      1696
           1       0.48      0.47      0.48       304

    accuracy                           0.84      2000
   macro avg       0.69      0.69      0.69      2000
weighted avg       0.84      0.84      0.84      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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ocEBYxRkafPbE4CTkdPR3BEAjabGqNaH+pdKS0vrtSivIeq+K7o9+KgCf/El6y1HRYX2PPznRo21ufjtqYXXXXedXnrpJX+dDgAA/+LZBB757amFubm5bmUNAABaEn9dWtgaeZ0MjBkzxu21YRg6dOiQNm/ezE2HAAA4CXmdDERERLi9DggIUI8ePTRr1iwNGzbMb4EBAICm4VUy4HA4dNNNN6lv377q0KFDY8UEAID/NfHVBCcTrxYQBgYGatiwYTydEABw0mnqRxifTLy+muDMM8/Unj17GiMWAADQDLxOBh5++GHdc889WrlypQ4dOiS73e62AQDQYnFZ4QnVe83ArFmzdPfdd+vyyy+XJF155ZVutyU2DEMWi0UOBzdIAQC0QKwZ8KjeycDMmTN166236oMPPmjMeAAAQBOrdzJQd9fiSy+9tNGCAQCgsXDTIc+8urTw155WCABAi0abwCOvkoEzzjjjNxOC4uJinwICAABNy6tkYObMmcfdgRAAgJMBbQLPvEoGxo0bp+jo6MaKBQCAxkObwKN632eA9QIAALROXl9NAADASYnKgEf1TgacTmdjxgEAQKNizYBnXj/CGACAkxKVAY+8fjYBAABoXagMAADMgcqARyQDAABTYM2AZ7QJAAAwOSoDAABzoE3gEckAAMAUaBN4RpsAAACTozIAADAH2gQekQwAAMyBZMAj2gQAAJgclQEAgClYftp8md9akQwAAMyBNoFHJAMAAFPg0kLPWDMAAIDJURkAAJgDbQKPSAYAAObRir/QfUGbAAAAk6MyAAAwBRYQekYyAAAwB9YMeESbAAAAk6MyAAAwBdoEnpEMAADMgTaBR7QJAAAwOZIBAIAp1LUJfNm8deDAAV133XXq2LGjwsLC1LdvX23evNl13DAMZWRkqHPnzgoLC1NSUpK+/vprt3MUFxcrJSVFVqtVkZGRSktLU1lZma8/DjckAwAAczD8sHnhyJEjuvDCC9WmTRu9++67+vLLL/X444+rQ4cOrjFz5sxRVlaWsrOztXHjRrVr107JycmqqKhwjUlJSdH27duVk5OjlStXat26dZowYUJDfwonxJoBAIA5+GnNgN1ud9sdEhKikJCQ44Y/9thjiouL08svv+zal5CQ8PPpDEMLFizQgw8+qFGjRkmSlixZopiYGK1YsULjxo1TQUGBVq1apU2b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qV+/fvrHP/7h9j7vvPOOzjjjDIWFhWnIkCFucdbXtGnTdMYZZ6ht27bq1q2bpk+frurq6uPGPfvss4qLi1Pbtm119dVXq7S01O34Cy+8oF69eik0NFQ9e/bU008/7XUsAJoPyQBMIywsTFVVVa7Xq1ev1s6dO5WTk6OVK1equrpaycnJCg8P1/r16/Xxxx+rffv2Gj58uGve448/rsWLF+ull17SRx99pOLiYr355pu/+r433HCD/v73vysrK0sFBQV69tln1b59e8XFxemNN96QJO3cuVOHDh3Sk08+KUnKzMzUkiVLlJ2dre3bt2vy5Mm67rrrtHbtWkm1ScuYMWN0xRVXKD8/X7fccovuu+8+r38m4eHhWrx4sb788ks9+eSTev755/XEE0+4jdm1a5dee+01vf3221q1apU+++wz3X777a7jS5cuVUZGhh555BEVFBTo0Ucf1fTp0/XKK694HQ+AZmIArVBqaqoxatQowzAMw+l0Gjk5OUZISIhxzz33uI7HxMQYlZWVrjl//etfjR49ehhOp9O1r7Ky0ggLCzPee+89wzAMo3PnzsacOXNcx6urq40uXbq43sswDOPSSy817rrrLsMwDGPnzp2GJCMnJ+eEcX7wwQeGJOPIkSOufRUVFUbbtm2NDRs2uI1NS0szrrnmGsMwDOP+++83evfu7XZ82rRpx53rf0ky3nzzTY/H586dawwYMMD1+qGHHjICAwON7777zrXv3XffNQICAoxDhw4ZhmEYp512mrFs2TK388yePdtITEw0DMMw9u7da0gyPvvsM4/vC6B5sWYArdbKlSvVvn17VVdXy+l06tprr9WMGTNcx/v27eu2TmDr1q3atWuXwsPD3c5TUVGh3bt3q7S0VIcOHdKgQYNcx4KCgjRw4MDjWgV18vPzFRgYqEsvvbTece/atUvHjh3TZZdd5ra/qqpKZ599tiSpoKDALQ5JSkxMrPd71Fm+fLmysrK0e/dulZWVqaamRlar1W1M165ddcopp7i9j9Pp1M6dOxUeHq7du3crLS1N48ePd42pqalRRESE1/EAaB4kA2i1hgwZomeeeUbBwcGy2WwKCnL/dW/Xrp3b67KyMg0YMEBLly497ly/+93vGhRDWFiY13PKysokSf/+97/dvoSl2nUQ/pKbm6uUlBTNnDlTycnJioiI0KuvvqrHH3/c61iff/7545KTwMBAv8UKoHGRDKDVateunbp3717v8eecc46WL1+u6Ojo4/46rtO5c2dt3LhRl1xyiaTav4Dz8vJ0zjnnnHB837595XQ6tXbtWiUlJR13vK4y4XA4XPt69+6tkJAQ7du3z2NFoVevXq7FkHU++eST3/6Qv7BhwwbFx8frgQcecO379ttvjxu3b98+HTx4UDabzfU+AQEB6tGjh2JiYmSz2bRnzx6lpKR49f4AWg4WEAI/SUlJUadOnTRq1CitX79ee/fu1Ycffqg777xT3333nSTprrvu0l/+8hetWLFCO3bs0O233/6r9wg49dRTlZqaqptvvlkrVqxwnfO1116TJMXHx8tisWjlypX6/vvvVVZWpvDwcN1zzz2aPHmyXnnlFe3evVtbtmzRwoULXYvybr31Vn399deaOnWqdu7cqWXLlmnx4sVefd7TTz9d+/bt06uvvqrdu3crKyvrhIshQ0NDlZqaqq1bt2r9+vW68847dfXVVys2NlaSNHPmTGVmZiorK0tfffWVtm3bppdfflnz58/3Kh4AzYdkAPhJ27ZttW7dOnXt2lVjxoxRr169lJaWpoqKClel4O6779b111+v1NRUJSYmKjw8XH/4wx9+9bzPPPOMrrrqKt1+++3q2bOnxo8fr/LycknSKaecopkzZ+q+++5TTEyM0tPTJUmzZ8/W9OnTlZmZqV69emn48OH697//rYSEBEm1ffw33nhDK1asUL9+/ZSdna1HH33Uq8975ZVXavLkyUpPT1f//v21YcMGTZ8+/bhx3bt315gxY3T55Zdr2LBhOuuss9wuHbzlllv0wgsv6OWXX1bfvn116aWXavHixa5YAbR8FsPTyicAAGAKVAYAADA5kgEAAEyOZAAAAJMjGQAAwORIBgAAMDmSAQAATI5kAAAAkyMZAADA5EgGAAAwOZIBAABMjmQAAACT+/+xp3EnzNc5VAAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scoring-metric:-ROC-AUC">Scoring metric: ROC AUC<a class="anchor-link" href="#Scoring-metric:-ROC-AUC">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">randomforest_gridsearch_roc</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(),</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">grid_rf</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;roc_auc_ovo_weighted&#39;</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="n">randomforest_gridsearch_roc</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">randomforest_gridsearch_roc</span><span class="o">.</span><span class="n">best_estimator_</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.91      0.91      0.91      1696
           1       0.50      0.52      0.51       304

    accuracy                           0.85      2000
   macro avg       0.71      0.71      0.71      2000
weighted avg       0.85      0.85      0.85      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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PqrVq1drwYIFCg4Odu0///zz9cILL/g1OAAA/Mfih6198joZWLNmjZ577jklJSUpMDDQtX/QoEH6/PPP/RocAAB+Q5vAI6+TgW+++UZ9+vQ5ab/T6XS7hSIAAGgbvE4G+vfvr3ffffek/X/729904YUX+iUoAAD8jsqAR15fgXDOnDlKTk7WN998I6fTqb///e/Kz8/XmjVrtGnTpqaIEQAA3xmWE5sv57dTXlcGxo4dq9dff13/+te/1KlTJ82ZM0d5eXl6/fXX9atf/aopYgQAAE3ojO5NcPnllysjI8PfsQAA0GS4hbFnZ3yjouzsbOXl5Uk6MY9gyJAhfgsKAAC/466FHnmdDHz99de6/vrr9f777ysiIkKSVFpaqksuuUQvv/yyzj77bH/HCAAAmpDXcwZuu+021dbWKi8vTyUlJSopKVFeXp6cTqduu+22pogRAADfNUwg9GVrp7yuDGzbtk3bt29X3759Xfv69u2rpUuX6vLLL/drcAAA+IvFOLH5cn575XUyEBsbe8qLC9XX18vhcPglKAAA/I45Ax553SZYuHCh7rzzTmVnZ7v2ZWdn6+6779aiRYv8GhwAAGh6jaoMREZGymL5oVdSWVmpuLg4BQWdOL2urk5BQUG69dZbNW7cuCYJFAAAn3DRIY8alQwsWbKkicMAAKCJ0SbwqFHJQHJyclPHAQAAWsgZX3RIkqqqqlRTU+O2z2q1+hQQAABNgsqAR15PIKysrFRqaqqio6PVqVMnRUZGum0AALRK3LXQI6+Tgfvuu09bt27V8uXLFRISohdeeEHz5s2Tw+HQmjVrmiJGAADQhLxuE7z++utas2aNhg0bpltuuUWXX365+vTpox49emjt2rVKSkpqijgBAPANqwk88royUFJSot69e0s6MT+gpKREknTZZZcpMzPTv9EBAOAnDVcg9GVrr7xOBnr37q0DBw5Iks477zy98sorkk5UDBpuXAQAANoOr5OBW265RR999JEkadasWVq2bJlCQ0M1bdo0zZgxw+8BAgDgF0wg9MjrOQPTpk1z/TshIUGff/65cnJy1KdPH11wwQV+DQ4AADQ9n64zIEk9evRQjx49/BELAABNxiIf71rot0han0YlA+np6Y1+wrvuuuuMgwEAAM2vUcnAU0891agns1gsLZIM/PrcgQqydGj21wWahcXZ0hEATcdo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p4iICEVFRWns2LE6ePCg6znr6+s1ffp0RUREqEuXLrrvvvv009t7/LRNUF1drZkzZyo2NlYhISHq06ePXnzxRR08eNB1c5zIyEhZLBbdfPPNkk7cIjotLU29evVSWFiYBg0apL/97W9ur/PGG2/o3HPPVVhYmIYPH+4WZ2PNnDlT5557rjp27KjevXtr9uzZqq2tPWncs88+q9jYWHXs2FHXXXedysrK3I6/8MIL6tevn0JDQ3Xeeefpj3/8o9exAGg5JAMwjbCwMNXU1Lgeb9myRfn5+crIyNCmTZtUW1urxMREhYeH691339X777+vzp07a9SoUa7znnzySa1evVorV67Ue++9p5KSEm3YsOG/vu7vfvc7/eUvf1F6erry8vL07LPPqnPnzoqNjdWrr74qScrPz9eRI0f09NNPS5LS0tK0Zs0arVixQnv27NG0adN04403atu2bZJOJC3jx4/X1VdfrdzcXN12222aNWuW13+T8PBwrV69Wp999pmefvppPf/883rqqafcxuzdu1evvPKKXn/9dW3evFkffvih7rjjDtfxtWvXas6cOXr00UeVl5enxx57TLNnz9ZLL73kdTwAWogBtEPJycnG2LFjDcMwDKfTaWRkZBghISHGvffe6zoeExNjVFdXu87505/+ZPTt29dwOp2ufdXV1UZYWJjx5ptvGoZhGN26dTMWLFjgOl5bW2ucffbZrtcyDMO48sorjbvvvtswDMPIz883JBkZGRmnjPPtt982JBlHjx517auqqjI6duxobN++3W1sSkqKcf311xuGYRj333+/0b9/f7fjM2fOPOm5fkqSsWHDBo/HFy5caAwZMsT1+KGHHjICAwONr7/+2rXvn//8pxEQEGAcOXLEMAzD+PnPf26sW7fO7XkefvhhIz4+3jAMwzhw4IAhyfjwww89vi6AlsWcAbRbmzZtUufOnVVbWyun06kbbrhBc+fOdR0fOHCg2zyBjz76SHv37lV4eLjb81RVVWnfvn0qKyvTkSNHFBcX5zoWFBSkoUOHntQqaJCbm6vAwEBdeeWVjY577969On78uH71q1+57a+pqdGFF14oScrLy3OLQ5Li4+Mb/RoN1q9fr/T0dO3bt08VFRWqq6uT1Wp1G9O9e3edddZZbq/jdDqVn5+v8PBw7du3TykpKZo0aZJrTF1dnWw2m9fxAGgZJANot4YPH67ly5crODhYDodDQUHuH/dOnTq5Pa6oqNCQIUO0du3ak57rZz/72RnFEBYW5vU5FRUVkqR//OMfbl/C0ol5EP6SlZWlpKQkzZs3T4mJibLZbHr55Zf15JNPeh3r888/f1JyEhgY6LdYATQtkgG0W506dVKfPn0aPf4Xv/iF1q9fr+jo6JN+HTfo1q2bduzYoSuuuELSiV/AOTk5+sUvfnHK8QMHDpTT6dS2bduUkJBw0vGGykR9fb1rX//+/RUSEqJDhw55rCj069fPNRmywQcffHD6N/kj27dvV48ePfTAAw+49n311VcnjTt06JAOHz4sh8Phep2AgAD17dtXMTExcjgc2r9/v5KSkrx6fQCtBxMIgf9ISkpS165dNXbsWL377rs6cOCA3nnnHd111136+uuvJUl33323Hn/8cW3cuFGff/657rjjjv96jYCePXsqOTlZt956qzZu3Oh6zldeeUWS1KNHD1ksFm3atEnffvutKioqFB4ernvvvVfTpk3TSy+9pH379mn37t1aunSpa1Le7bffri+//FIzZsxQfn6+1q1bp9WrV3v1fs855xwdOnRIL7/8svbt26f09PRTToYMDQ1VcnKyPvroI7377ru66667dN1118lut0uS5s2bp7S0NKWnp+uLL77QJ598olWrVmnx4sVexQOg5ZAMAP/RsWNHZWZmqnv37ho/frz69eunlJQUVVVVuSoF99xzj2666SYlJycrPj5e4eHh+vWvf/1fn3f58uW69tprdccdd+i8887TpEmTVFlZKUk666yzNG/ePM2aNUsxMTFKTU2VJD388MOaPXu20tLS1K9fP40aNUr/+Mc/1KtXL0kn+vivvvqqNm7cqEGDBmnFihV67LHHvHq/11xzjaZNm6bU1FQNHjxY27dv1+zZs08a16dPH40fP15XXXWVRo4cqQsuuMBt6eBtt92mF154QatWrdLAgQN15ZVXavXq1a5YAbR+FsPTzCcAAGAKVAYAADA5kgEAAEyOZAAAAJMjGQAAwORIBgAAMDmSAQAATI5kAAAAkyMZAADA5EgGAAAwOZIBAABMjmQAAACT+/8eJIJtEYMzfwAAAABJRU5ErkJggg==
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>In the above 2 scenarios, we find our model performance improved quite a bit with regards to the minority class (label 1) although it might lead to a drop in accuracy due to some more 0 labels being misclassified. But as stated before, in such problems there will a certain tolerance towards that. Associating example, rejecting a loan for someone who can repay it (majority class) is less risky for a bank than approving it for someone who cannot pay it back (minority class).</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Synthetic-Minority-oversampling-technique-(SMOTE)"><strong>Synthetic Minority oversampling technique (SMOTE)</strong><a class="anchor-link" href="#Synthetic-Minority-oversampling-technique-(SMOTE)">&#182;</a></h1>
</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>When it comes to tackling imbalance in label classes, a very common technique is random over sampling. In this, random entries with the minority class label are duplicated in the training set so that its number can match up to that of the majority class. While this method may be useful in image classifications along with some rotation and skew, it definitely does not add any new information in our current problem to help us predict the minority class better. Therefore we choose SMOTE to create synthetic samples of the minority class.</p>
<p>SMOTE uses k-nearest neighbors to determine the samples closest to randomly chosen samples and creates new synthetic samples on the line joining the closest samples in the feature space. There is a great documentation on SMOTE along with visualisations of how it works which can be found <a href="https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/">here.</a> Alternatively, you can just type SMOTE on google and this will be one of the first results.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Oversampling-minority-class">Oversampling minority class<a class="anchor-link" href="#Oversampling-minority-class">&#182;</a></h2>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Oversampling minority class to match with the number of samples of majority class</span>

<span class="n">oversampler</span> <span class="o">=</span> <span class="n">SMOTE</span><span class="p">(</span><span class="n">sampling_strategy</span><span class="o">=</span><span class="s1">&#39;auto&#39;</span><span class="p">,</span> <span class="n">k_neighbors</span><span class="o">=</span><span class="mi">3</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Before oversampling: &#39;</span><span class="p">,</span> <span class="n">Counter</span><span class="p">(</span><span class="n">y_train</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]))</span>

<span class="n">X_train_os</span><span class="p">,</span> <span class="n">y_train_os</span> <span class="o">=</span> <span class="n">oversampler</span><span class="o">.</span><span class="n">fit_resample</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;After oversampling: &#39;</span><span class="p">,</span> <span class="n">Counter</span><span class="p">(</span><span class="n">y_train_os</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Before oversampling:  Counter({0: 6704, 1: 1296})
After oversampling:  Counter({0: 6704, 1: 6704})
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># trying base classifier on oversampled training set</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">RandomForestClassifier</span><span class="p">()</span>
<span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train_os</span><span class="p">,</span> <span class="n">y_train_os</span><span class="p">)</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.93      0.88      0.90      1696
           1       0.47      0.62      0.54       304

    accuracy                           0.84      2000
   macro avg       0.70      0.75      0.72      2000
weighted avg       0.86      0.84      0.85      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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AABAw+FxMjB69Gh9+eWXkqSpU6cqNTVVwcHBmjhxoiZPnuzzAAEA8AkGELrlcTIwceJEPfDAA5Kk+Ph47dmzRytXrtQXX3yhBx980OcBAgDQENntdk2bNk0dOnRQSEiILr74Ys2aNUuG8XNWYRiGUlJS1Lp1a4WEhCg+Pl779u1zeU5+fr4SExNltVoVFhamMWPGqLi42KexerXOgCS1a9dO7dq180UsAADUGou83LXQw/bPPPOMFi9erNdee009evTQjh07NHr0aNlsNucf1XPmzNHChQv12muvqUOHDpo2bZoSEhL07bffKjg4WJKUmJioY8eOKT09XRUVFRo9erTGjRunlStXnv+H+ZUaJQMLFy6s8QOrPyAAAGa2detWDR8+XMOGDZMktW/fXq+//ro+//xzSVVVgfnz5+vxxx/X8OHDJUkrVqxQZGSk1qxZo1GjRmn37t1av369tm/frr59+0qSFi1apKFDh+rZZ5/12W7BNUoGnn/++Ro9zGKx1Eky8MdLeirA0uSCvy9wIfi3rKzrEIDa47iAv98+mlpYVFTkcjooKEhBQUFnNL/mmmu0dOlS7d27V5dccom+/PJLffLJJ5o3b54k6dChQ8rJyVF8fLzzHpvNptjYWGVkZGjUqFHKyMhQWFiYMxGQqrro/fz8tG3bNv3xj388/8/zCzVKBqpnDwAA0GD5aDnimJgYl9PTp0/XjBkzzmg+depUFRUVqWvXrvL395fdbtdTTz3lXI8nJydHkhQZGelyX2RkpPNaTk6OIiIiXK4HBAQoPDzc2cYXvB4zAACAmRw5csRlH56zVQUk6c0331RaWppWrlypHj16KCsrSxMmTFB0dHS92wCQZAAAYA4+qgxYrdYabco3efJkTZ06VaNGjZIk9ezZU99//71mz56tpKQkRUVFSZJyc3PVunVr5325ubnq3bu3JCkqKkp5eXkuz62srFR+fr7zfl/weGohAAAN0YVegfDUqVPy83P9mvX395fD4ZAkdejQQVFRUdqwYYPzelFRkbZt26a4uDhJUlxcnAoKCpSZmelss3HjRjkcDsXGxp7nT+JMVAYAAKgFN954o5566im1bdtWPXr00BdffKF58+bp7rvvllQ16H7ChAl68skn1blzZ+fUwujoaI0YMUKS1K1bNw0ePFhjx47VkiVLVFFRoeTkZI0aNcpnMwkk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8uUXPiDgAiMZAADA5BgzAACAyZEMAABgciQDAACYHMkAAAAmRzIAAIDJkQwAAGByJAMAAJgcyQAAACZHMgB46a677tKIESOcr/v3768JEyZc8Dg+/vhjWSwWFRQUuG1jsVi0Zs2aGj9zxowZ6t27t1dxfffdd7JYLMrKyvLqOQBqD8kAGqW77rpLFotFFotFgYGB6tSpk5544glVVlbW+nu//fbbmjVrVo3a1uQLHABqGxsVodEaPHiwXn31VZWVlendd9/V+PHj1aRJEz366KNntC0vL1dgYKBP3jc8PNwnzwGAC4XKABqtoKAgRUVFqV27drr33nsVHx+vd955R9LPpf2nnnpK0dHR6tKliyTpyJEjuvXWWxUWFqbw8HANHz5c3333nfOZdrtdkyZNUlhYmFq2bKlHHnlEv97e49fdBGVlZZoyZYpiYmIUFBSkTp066W9/+5u+++475+Y4LVq0kMVi0V133SWpaovo2bNnq0OHDgoJCVGvXr30z3/+0+V93n33XV1yySUKCQnRgAEDXOKsqSlTpuiSSy5R06ZN1bFjR02bNk0VFRVntHvppZcUExOjpk2b6tZbb1VhYaHL9VdeeUXdunVTcHCwunbtqhdffNHjWADUHZIBmEZISIjKy8udrzds2KDs7Gylp6dr3bp1qqioUEJCgkJDQ7VlyxZ9+umnat68uQYPHuy877nnntPy5cu1bNkyffLJJ8rPz9fq1at/833vvPNOvf7661q4cKF2796tl156Sc2bN1dMTIzeeustSVJ2draOHTumBQsWSJJmz56tFStWaMmSJdq1a5cmTpyo22+/XZs2bZJUlbTcfPPNuvHGG5WVlaV77rlHU6dO9fhnEhoaquXLl+vbb7/VggUL9PLLL+v55593abN//369+eabWrt2rdavX68vvvhC9913n/N6WlqaUlJS9NRTT2n37t16+umnNW3aNL322msexwOgjhhAI5SUlGQMHz7cMAzDcDgcRnp6uhEUFGQ8/PDDzuuRkZFGWVmZ856///3vRpcuXQyHw+E8V1ZWZoSEhBjvv/++YRiG0bp1a2POnDnO6xUVFUabNm2c72UYhnHDDTcYDz74oGEYhpGdnW1IMtLT088a50cffWRIMk6cOOE8V1paajRt2tTYunWrS9sxY8YYf/7znw3DMIxHH33U6N69u8v1KVOmnPGsX5NkrF692u31uXPnGn369HG+nj59uuHv72/88MMPznPvvfee4efnZxw7dswwDMO4+OKLjZUrV7o8Z9asWUZcXJxhGIZx6NAhQ5LxxRdfuH1fAHWLMQNotNatW6fmzZuroqJCDodDt912m2bMmOG83rNnT5dxAl9++aX279+v0NBQl+eUlpbqwIEDKiws1LFjxxQbG+u8FhAQoL59+57RVVAtKytL/v7+uuGGG2oc9/79+3Xq1Cn94Q9/cDlfXl6uyy+/XJK0e/dulzgkKS4ursbvUW3VqlVauHChDhw4oOLiYlVWVspqtbq0adu2rS666CKX93E4HMrOzlZoaKgOHDigMWPGaOzYsc42lZWVstlsHscDoG6QDKDRGjBggBYvXqzAwEBFR0crIMD1171Zs2Yur4uLi9WnTx+lpaWd8azf/e535xVDSEiIx/cUFxdLkv71r3+5fAlLVeMgfCUjI0OJiYmaOXOmEhISZLPZ9MYbb+i5557zONaXX375jOTE39/fZ7ECqF0kA2i0mjVrpk6dOtW4/RVXXKFVq1YpIiLijL+Oq7Vu3Vrbtm1Tv379JFX9BZyZmakrrrjirO179uwph8OhTZs2KT4+/ozr1ZUJu93uPNe9e3cFBQXp8OHDbisK3bp1cw6GrPbZZ5+d+0P+wtatW9WuXTs99thjznPff//9Ge0OHz6so0ePKjo62vk+fn5+6tKliyIjIxUdHa2DBw8qMTHRo/cHUH8wgBD4j8TERLVq1UrDhw/Xli1bdOjQIX388cd64IEH9MMPP0iSHnzwQf31r3/VmjVrtGfPHt13332/uUZA+/btlZSUpLvvvltr1qxxPvPNN9+UJLVr104Wi0Xr1q3T8ePHVVxcrNDQUD388MOaOHGiXnvtNR04cEA7d+7UokWLnIPy/vKXv2jfvn2aPHmysrOztXLlSi1fvtyjz9u5c2cdPnxYb7zxhg4cOKCFCxeedTBkcHCwkpKS9OWXX2rLli164IEHdOuttyoqKkqSNHPmTM2ePVsLFy7U3r179fXXX+vVV1/VvHnzPIoHQN0hGQD+o2nTptq8ebPatm2rm2++Wd26ddOYMWNUWlrqrBQ89NBDuuOOO5SUlKS4uDiFhobqj3/8428+d/Hixbrlllt03333qWvXrho7dqxKSkokSRdddJFmzpypqVOnKjIyUsnJyZKkWbNmadq0aZo9e7a6deumwYMH61//+pc6dOggqaof/6233tKaNWvUq1cvLVmyRE8//bRHn/emm27SxIkTlZycrN69e2vr1q2aNm3aGe06deqkm2++WUOHDtWgQYN02WWXuUwdvOeee/TKK6/o1VdfVc+ePXXDDTdo+fLlzlgB1H8Ww93IJwAAYApUBgAAMDmSAQAATI5kAAAAkyMZAADA5EgGAAAwOZIBAABMjmQAAACTIxkAAMDkSAYAADA5kgEAAEyOZAAAAJP7/9haQzRhlT8+AAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>It is already better than our last base classifier performance and all previous tuned classifiers. Until now we have only oversampled the minority class. But the research paper on SMOTE recommends not to oversample to completely match the number of samples but only till a fraction of the majority class to avoid making too many synthetic samples that never occur in real life. Follwed by undersampling of the majority class. It might seem a bit confusing in words and perhaps easier to follow in the code below.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Oversampling-minority-class-and-undersampling-majority-class">Oversampling minority class and undersampling majority class<a class="anchor-link" href="#Oversampling-minority-class-and-undersampling-majority-class">&#182;</a></h2>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Oversampling minority class to have 30% of the total samples in majority class</span>
<span class="c1"># undersampling the majority class to have 60% more samples than the majority class</span>
<span class="c1"># the above percentages have been chosen by me to have close but not equal number of samples in both classes.</span>

<span class="n">oversampler</span> <span class="o">=</span> <span class="n">SMOTE</span><span class="p">(</span><span class="n">sampling_strategy</span><span class="o">=</span><span class="mf">0.3</span><span class="p">,</span> <span class="n">k_neighbors</span><span class="o">=</span><span class="mi">3</span><span class="p">)</span>
<span class="n">undersampler</span> <span class="o">=</span> <span class="n">RandomUnderSampler</span><span class="p">(</span><span class="n">sampling_strategy</span><span class="o">=</span><span class="mf">0.6</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Before synthetic oversampling: &#39;</span><span class="p">,</span> <span class="n">Counter</span><span class="p">(</span><span class="n">y_train</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]))</span>

<span class="n">X_train_os</span><span class="p">,</span> <span class="n">y_train_os</span> <span class="o">=</span> <span class="n">oversampler</span><span class="o">.</span><span class="n">fit_resample</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span> <span class="n">y_train</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;After oversampling minority class: &#39;</span><span class="p">,</span> <span class="n">Counter</span><span class="p">(</span><span class="n">y_train_os</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]))</span>

<span class="n">X_train_os_us</span><span class="p">,</span> <span class="n">y_train_os_us</span> <span class="o">=</span> <span class="n">undersampler</span><span class="o">.</span><span class="n">fit_resample</span><span class="p">(</span><span class="n">X_train_os</span><span class="p">,</span> <span class="n">y_train_os</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;After undersampling majority class: &#39;</span><span class="p">,</span> <span class="n">Counter</span><span class="p">(</span><span class="n">y_train_os_us</span><span class="p">[</span><span class="s1">&#39;Response&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Before synthetic oversampling:  Counter({0: 6704, 1: 1296})
After oversampling minority class:  Counter({0: 6704, 1: 2011})
After undersampling majority class:  Counter({0: 3351, 1: 2011})
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># trying base model</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">RandomForestClassifier</span><span class="p">()</span>
<span class="n">model</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train_os_us</span><span class="p">,</span> <span class="n">y_train_os_us</span><span class="p">)</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.95      0.83      0.89      1696
           1       0.46      0.77      0.57       304

    accuracy                           0.82      2000
   macro avg       0.70      0.80      0.73      2000
weighted avg       0.88      0.82      0.84      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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2rVLb775pubNm6dx48a5FStzBgAApvDbSYBne707tm7dqt69ezteV35BJycna+nSpXr44YdVXFysESNGKD8/X1dddZXWrFmj4OBgxzXLly9XSkqKrr32Wvn5+Wnw4MGaP3++47zVatXHH3+sUaNGqXv37mrWrJkmT57s1rJCSbIYhlFnn71QWFgoq9Wq49+1VVgoRQ7UT30H3OHrEIBqU2Er0afpM1RQUOA0Kc+bKr8rerw7RgGNzn6yX0VxqbYOmlutsfoKlQEAgCnUdGWgLuHnNAAAJkdlAABgCoaHKwLqc2WAZAAAYAqGJE9mydXZCXZVwDABAAAmR2UAAGAKdllk0dmX+u0eXFvbkQwAAEyB1QSuMUwAAIDJURkAAJiC3bDI4sGve28+m6C2IRkAAJiCYXi4mqAeLydgmAAAAJOjMgAAMAUmELpGMgAAMAWSAddIBgAApsAEQteYMwAAgMlRGQAAmAKrCVwjGQAAmMKpZMCTOQNeDKaWYZgAAACTozIAADAFVhO4RjIAADAF43/Nk+vrK4YJAAAwOSoDAABTYJjANZIBAIA5ME7gEskAAMAcPKwMqB5XBpgzAACAyVEZAACYAjsQukYyAAAwBSYQusYwAQAAJkdlAABgDobFs0mA9bgyQDIAADAF5gy4xjABAAAmR2UAAGAObDrkUpWSgffee6/KN7zpppvOOhgAAKoLqwlcq1IyMHDgwCrdzGKxyGazeRIPAACoYVVKBux2e3XHAQBA9avHpX5PeDRnoKSkRMHBwd6KBQCAasMwgWturyaw2Wx64okndO6556px48b6/vvvJUmTJk3Sv/71L68HCACAVxheaPWU28nAU089paVLl2rmzJkKDAx0HL/wwgv18ssvezU4AABQ/dxOBpYtW6YXX3xRSUlJ8vf3dxzv2rWr9uzZ49XgAADwHosXWv3k9pyBI0eOqF27dqcdt9vtKi8v90pQAAB4HfsMuOR2ZaBTp07auHHjacf//e9/6+KLL/ZKUAAAoOa4XRmYPHmykpOTdeTIEdntdr377rvKzMzUsmXLtHr16uqIEQAAz1EZcMntysCAAQP0/vvv65NPPlGjRo00efJk7d69W++//76uu+666ogRAADPVT610JNWT53VPgNXX321UlNTvR0LAADwgbN+auHWrVv12muv6bXXXlN6ero3YwIAwOsqH2Hs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1759+1RUVKROnTqpcePG1REfAABewZwB1856B8LAwEB16tTJm7EAAFB92I7YJbeTgd69e8ticT2JYt26dR4FBAAAapbbyUC3bt2cXpeXlysjI0M7d+5UcnKyt+ICAMC7PBwmoDLwG3PmzDnj8SlTpqioqMjjgAAAqBYME7jktQcV3X777XrllVe8dTsAAFBDvPYI47S0NAUHB3vrdgAAeBeVAZfcTgYGDRrk9NowDB07dkxbt27VpEmTvBYYAADexNJC19xOBqxWq9NrPz8/tW/fXtOmTVOfPn28FhgAAKgZbiUDNptNQ4cOVZcuXdSkSZPqigkAANQgtyYQ+vv7q0+fPjydEABQ9/BsApfcXk1w4YUX6vvvv6+OWAAAqDaVcwY8afWV28nAk08+qYceekirV6/WsWPHVFhY6NQAAEDdUuU5A9OmTdODDz6o66+/XpJ00003OW1LbBiGLBaLbDab96MEAMAb6vGve09UORmYOnWq/v73v+vTTz+tzngAAKge7DPgUpWTAcM49Ve45pprqi0YAABQ89xaWvhHTysEAKA2Y9Mh19xKBi644II/TQjy8vI8CggAgGrBMIFLbiUDU6dOPW0HQgAAULe5lQwMGTJEkZGR1RULAADVhmEC16qcDDBfAABQpzFM4FKVNx2qXE0AAADqlyonA3a7nSECAEDd5YNnExw5ckS33367mjZtqpCQEHXp0kVbt279NSTD0OTJk9W8eXOFhIQoISFBe/fudbpHXl6ekpKSFBYWpvDwcA0bNkxFRUXuB/MH3N6OGACAuqimn01w/PhxXXnllWrQoIE+/PBDffvtt3r22Wednvo7c+ZMzZ8/X4sXL9amTZvUqFEjJSYmqqSkxNEnKSlJu3btUmpqqlavXq0NGzZoxIgR3vqzSHJzAiEAAHVWDc8ZePrppxUbG6slS5Y4jrVp0+bX2xmG5s6dq8cee0wDBgyQJC1btkxRUVFatWqVhgwZot27d2vNmjXasmWLevToIUlasGCBrr/+ej3zzDOKiYnx4AP9isoAAABu+P0D+kpLS8/Y77333lOPHj30t7/9TZGRkbr44ov10ksvOc4fOHBA2dnZSkhIcByzWq2Ki4tTWlqaJCktLU3h4eGORECSEhIS5Ofnp02bNnntM5EMAADMwUtzBmJjY2W1Wh1txowZZ3y777//XosWLdL555+v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u+xjsVi0atWqKt9zypQp6tatm0dxHTx4UBaLRRkZGR7dB0D1IRlAvXTXXXfJYrHIYrEoMDBQ7dq107Rp01RRUVHt7/3uu+/qiSeeqFLfqnyBA0B149kEqLf69u2rJUuWqLS0VB988IFGjRqlBg0aaOLEiaf1LSsrU2BgoFfeNyIiwiv3AYCaQmUA9VZQUJCio6PVqlUrjRw5UgkJCXrvvfck/Vraf+qppxQTE6P27dtLkrKysnTLLbcoPDxcERERGjBggA4ePOi4p81m07hx4xQeHq6mTZvq4Ycf1u939P79MEFpaakmTJig2NhYBQUFqV27dvrXv/6lgwcPOvbDb9KkiSwWi+666y5Jp54KOWPGDLVp00YhISHq2rWr/v3vfzu9zwcffKALLrhAISEh6t27t1OcVTVhwgRdcMEFatiwodq2batJkyapvLz8tH4vvPCCYmNj1bBhQ91yyy0qKChwOv/yyy+rY8eOCg4OVocOHfT888+7HQsA3yEZgGmEhISorKzM8Xrt2rXKzMxUamqqVq9erfLyciUmJio0NFQbN27UF198ocaNG6tv376O65599lktXbpUr7zyij7//HPl5eVp5cqVf/i+d955p15//XXNnz9fu3fv1gsvvKDGjRsrNjZW77zzjiQpMzNTx44d07x58yRJM2bM0LJly7R48WLt2rVLY8eO1e23367169dLOpW0DBo0SDfeeKMyMjJ0zz336JFHHnH7bxIaGqqlS5fq22+/1bx58/TSSy9pzpw5Tn327dunt956S++//77WrFmjr7/+Wvfdd5/j/PLlyzV58mQ99dRT2r17t6ZPn65Jkybp1VdfdTseAD5iAPVQcnKyMWDAAMMwDMNutxupqalGUFCQ8dBDDznOR0VFGaWlpY5rXnvtNaN9+/aG3W53HCstLTVCQkKMjz76yDAMw2jevLkxc+ZMx/ny8nKjRYsWjvcyDMO45pprjAceeMAwDMPIzMw0JBmpqalnjPPTTz81JBnHjx93HCspKTEaNmxofPnll059hw0bZtx6662GYRjGxIkTjU6dOjmdnzBhwmn3+j1JxsqVK12enzVrltG9e3fH68cff9zw9/c3fvjhB8exDz/80PDz8zOOHTtmGIZhnHfeecaKFSuc7vPEE08Y8fHxhmEYxoEDBwxJxtdff+3yfQH4FnMGUG+tXr1ajRs3Vnl5uex2u2677TZNmTLFcb5Lly5O8wS2b9+uffv2KTQ01Ok+JSUl2r9/vwoKCnTs2DGnxzYHBASoR48epw0VVMrIyJC/v7+uueaaKse9b98+nTx5Utddd53T8bKyMl188cWSpN27d5/2+Oj4+Pgqv0elN998U/Pnz9f+/ftVVFSkiooKhYWFOfVp2bKlzj33XKf3sdvtyszMVGhoqPbv369hw4Zp+PDhjj4VFRWyWq1uxwPAN0gGUG/17t1bixYtUmBgoGJiYhQQ4PzPvVGjRk6vi4qK1L17dy1fvvy0e51zzjlnFUNISIjb1xQVFUmS/vvf/zp9CUun5kF4S1pampKSkjR16lQlJibKarXqjTfe0LPPPut2rC+99NJpyYm/v7/XYgVQvUgGUG81atRI7dq1q3L/Sy65RG+++aYiIyNP+3VcqXnz5tq0aZN69uwp6dQv4PT0dF1yySVn7N+lSxfZ7XatX79eCQkJp52vrEzYbDbHsU6dOikoKEiHDx92WVHo2LGjYzJkpa+++urPP+RvfPnll2rVqpUeffRRx7FDhw6d1u/w4cM6evSoYmJiHO/j5+en9u3bKyoqSjExMfr++++VlJTk1vsDqD2YQAj8T1JSkpo1a6YBAwZo48aNOnDggD777DONHj1aP/zwgyTpgQce0D//+U+tWrVKe/bs0X333feHewS0bt1aycnJuvvuu7Vq1SrHPd966y1JUqtWrWSxWLR69Wr9+OOPKioqUmhoqB566CGNHTtWr776qvbv369t27ZpwYIFjkl5f//737V3716NHz9emZmZWrFihZYuXerW5z3//PN1+PBhvfHGG9q/f7/mz59/xsmQwcHBSk5O1vbt27Vx40aNHj1at9xyi6KjoyVJU6dO1YwZMzR//nx999132rFjh5YsWaLZs2e7FQ8A3yEZAP6nYcOG2rBhg1q2bKlBgwapY8eOGjZsmEpKShyVggcffFB33HGHkpOTFR8fr9DQUP31r3/9w/suWrRIN998s+677z516NBBw4cPV3FxsSTp3HPP1dSpU/XII48oKipKKSkpkqQnnnhCkyZN0owZM9SxY0f17dtX//3vf9WmTRtJp8bx33nnHa1atUpdu3bV4sWLNX36dLc+70033aSxY8cqJSVF3bp105dffqlJkyad1q9du3YaNGiQrr/+evXp00cXXXSR09LBe+65Ry+//LKWLFmiLl266JprrtHSpUsdsQKo/SyGq5lPAADAFKgMAABgciQDAACYHMkAAAAmRzIAAIDJkQwAAGByJAMAAJgcyQAAACZHMgAAgMmRDAAAYHIkAwAAmBzJAAAAJkcyAACAyf1/YoR/jO6fQSEAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>And you can see the difference for yourself. Although the accuracy decreased a little bit, the model performance on the minority class improved a lot. Another vital thing to note is that synthetic oversampling should be performed only on training set and never on the test set.</p>
<p>Having said that, let's try tuning the model parameters with different scoring parameters as we did before.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scoring-metric:-F-score">Scoring metric: F-score<a class="anchor-link" href="#Scoring-metric:-F-score">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">randomforest_gridsearch_f1_os_us</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(),</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">grid_rf</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;f1_weighted&#39;</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="n">randomforest_gridsearch_f1_os_us</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train_os_us</span><span class="p">,</span> <span class="n">y_train_os_us</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">randomforest_gridsearch_f1_os_us</span><span class="o">.</span><span class="n">best_estimator_</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.96      0.83      0.89      1696
           1       0.45      0.79      0.58       304

    accuracy                           0.82      2000
   macro avg       0.71      0.81      0.73      2000
weighted avg       0.88      0.82      0.84      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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AQAATI5kAAAAkyMZAADA5EgGAAAwOZIBAABMjmQAAACTIxkAAMDkSAYAD919990aPXq04/XgwYM1derUOo/jgw8+kMViUX5+vss5FotFGzdurPE5586dq379+nkU17Fjx2SxWJSRkeHReQDUHpIBNEl33323LBaLLBaL/P391bVrV82fP18VFRW1/t7/+te/tGDBghrNrckXOADUNh5UhCZr2LBheuONN1RaWqr//Oc/SkhIULNmzTRr1qzz5paVlcnf398r7xsaGuqV8wBAXaEygCYrICBA4eHh6tixoyZPnqyYmBi99dZbkn4o7T/55JOKiIhQ9+7dJUknTpzQbbfdppCQEIWGhmrUqFE6duyY45yVlZWaPn26QkJC1Lp1az3yyCP66eM9ftomKC0t1cyZMxUZGamAgAB17dpVf/7zn3Xs2DHHw3FatWoli8Wiu+++W1LVI6KTkpLUuXNnBQUFqW/fvvrHP/7h9D7/+c9/dPnllysoKEhDhgxxirOmZs6cqcsvv1zNmzdXly5dNHv2bJWXl5837+WXX1ZkZKSaN2+u2267TQUFBU77X3vtNfXs2VOBgYHq0aOHXnrpJbdjAVB/SAZgGkFBQSorK3O83rp1qzIzM5WcnKzNmzervLxcsbGxCg4O1o4dO/TRRx+pZcuWGjZsmOO45557TqtWrdLrr7+uDz/8UHl5edqwYcPPvu9dd92lv/71r1q2bJkOHjyol19+WS1btlRkZKT++c9/SpIyMzN15swZPf/885KkpKQkrVmzRitXrtT+/fs1bdo03XHHHdq+fbukqqRlzJgxGjlypDIyMnTvvffq0UcfdftnEhwcrFWrVunAgQN6/vnn9eqrr2rJkiVOc44cOaI333xTmzZt0pYtW/TJJ5/o/vvvd+xfu3at5syZoyeffFIHDx7UU089pdmzZ2v16tVuxwOgnhhAExQfH2+MGjXKMAzDsNvtRnJyshEQEGA8/PDDjv1hYWFGaWmp45i//OUvRvfu3Q273e4YKy0tNYKCgox33nnHMAzDaNeunbFo0SLH/vLycuPSSy91vJdhGMaNN95oTJkyxTAMw8jMzDQkGcnJyReM8/333zckGWfPnnWMlZSUGM2bNzd27tzpNHfChAnGH/7wB8MwDGPWrFlGr169nPbPnDnzvHP9lCRjw4YNLvc/88wzRv/+/R2vn3jiCcPX19c4efKkY+ztt982fHx8jDNnzhiGYRiXXXaZsW7dOqfzLFiwwIiOjjYMwzCOHj1qSDI++eQTl+8LoH6xZgBN1ubNm9WyZUuVl5fLbrfr9ttv19y5cx37+/Tp47RO4NNPP9WRI0cUHBzsdJ6SkhJ9+eWXKigo0JkzZxQVFeXY5+fnpwEDBpzXKqiWkZEhX19f3XjjjTWO+8iRI/r222/1m9/8xmm8rKxMV111lSTp4MGDTnFIUnR0dI3fo9r69eu1bNkyffnllyoqKlJFRYWsVqvTnA4dOqh9+/ZO72O325WZmang4GB9+eWXmjBhgiZOnOiYU1FRIZvN5nY8AOoHyQCarCFDhmjFihXy9/dXRESE/Pycf91btGjh9LqoqEj9+/fX2rVrzzvXJZdcclExBAUFuX1MUVGRJOnf//6305ewVLUOwltSU1MVFxenefPmKTY2VjabTX/729/03HPPuR3rq6++el5y4uvr67VYAdQukgE0WS1atFDXrl1rPP/qq6/W+vXr1bZt2/P+Oq7Wrl07paWladCgQZKq/gJOT0/X1VdffcH5ffr0kd1u1/bt2xUTE3Pe/urKRGVlpWOsV69eCggIUFZWlsuKQs+ePR2LIat9/PHHv/whf2Tnzp3q2LGjHnvsMcfY8ePHz5uXlZWl06dPKyIiwvE+Pj4+6t69u8LCwhQREaGvvvpKcXFxbr0/gIaDBYTA9+Li4tSmTRuNGjVKO3bs0NGjR/XBBx/owQcf1MmTJyVJU6ZM0Z/+9Cdt3LhRhw4d0v333/+z9wjo1KmT4uPjdc8992jjxo2Oc7755puSpI4dO8pisWjz5s36+uuvVVRUpODgYD388MOaNm2aVq9erS+//FJ79+7VCy+84FiUd9999+nw4cOaMWOGMjMztW7dOq1atcqtz9utWzdlZWXpb3/7m7788kstW7bsgoshAwMDFR8fr08//VQ7duzQgw8+qNtuu03h4eGSpHnz5ikpKUnLli3TF198oX379umNN97Q4sWL3YoHQP0hGQC+17x5c6WkpKhDhw4aM2aMevbsqQkTJqikpMRRKXjooYd05513Kj4+XtHR0QoODtatt976s+ddsWKFfve73+n+++9Xjx49NHHiRBUXF0uS2rdvr3nz5unRRx9VWFiYEhMTJUkLFizQ7NmzlZSUpJ49e2rYsGH697//rc6dO0uq6uP/85//1MaNG9W3b1+tXLlSTz31lFuf95ZbbtG0adOUmJiofv36aefOnZo9e/Z587p27aoxY8ZoxIgRGjp0qK688kqnSwfvvfdevfbaa3rjjTfUp08f3XjjjVq1apUjVgANn8VwtfIJAACYApUBAABMjmQAAACTIxkAAMDkSAYAADA5kgEAAEyOZAAAAJMjGQAAwORIBgAAMDmSAQAATI5kAAAAkyMZAADA5P4/qakC+NBynu0AAAAASUVORK5CYII=
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Scoring-metric:-Precision">Scoring metric: Precision<a class="anchor-link" href="#Scoring-metric:-Precision">&#182;</a></h3>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">randomforest_gridsearch_pres_os_us</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestClassifier</span><span class="p">(),</span> <span class="n">param_grid</span><span class="o">=</span><span class="n">grid_rf</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s1">&#39;precision_weighted&#39;</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">4</span><span class="p">)</span>
<span class="n">randomforest_gridsearch_pres_os_us</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train_os_us</span><span class="p">,</span> <span class="n">y_train_os_us</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span> <span class="o">=</span> <span class="n">randomforest_gridsearch_pres_os_us</span><span class="o">.</span><span class="n">best_estimator_</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">model</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">classification_report</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span>
<span class="n">metrics</span><span class="o">.</span><span class="n">ConfusionMatrixDisplay</span><span class="p">(</span><span class="n">confusion_matrix</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">confusion_matrix</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">))</span><span class="o">.</span><span class="n">plot</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>              precision    recall  f1-score   support

           0       0.95      0.83      0.89      1696
           1       0.45      0.78      0.57       304

    accuracy                           0.82      2000
   macro avg       0.70      0.81      0.73      2000
weighted avg       0.88      0.82      0.84      2000

</pre>
</div>
</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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t9+u4OBghYSEaMiQIfr+++/t96ysrNSUKVMUHBysli1b6pFHHtGvd/T+9TBBaWmppk2bpsjISPn5+al9+/Z67bXX9P3339v3w2/RooUsFovuueceSWeeCpmYmKh27dopICBA3bt31z//+U+H93n//fd1+eWXKyAgQH379nWIs7qmTZumyy+/XE2bNtUll1yi6dOnq7y8/Kx2L730kiIjI9W0aVPdfvvtKigocLj+6quvqlOnTvL391fHjh314osvuhwLgLpDMgDTCAgIUFlZmf31pk2blJGRoeTkZG3YsEHl5eWKjY1VYGCgtm3bpk8//VTNmzfXgAED7P2ee+45rVy5Uq+//rq2b9+uvLw8rVu37jff9+6779bf//53JSUl6eDBg3rppZfUvHlzRUZG6l//+pckKSMjQydOnNDixYslSYmJiVq9erWWL1+uAwcOaPLkybrrrru0detWSWeSlmHDhunmm29Wenq67rvvPj366KMu/0wCAwO1cuVKffXVV1q8eLFeeeUVPf/88w5tDh8+rLfeekvvvvuuNm7cqM8//1wPPPCA/fqaNWs0Y8YMzZkzRwcPHtTcuXM1ffp0rVq1yuV4ANQRA2iE4uPjjSFDhhiGYRg2m81ITk42/Pz8jIcffth+PSwszCgtLbX3+dvf/mZ06NDBsNls9nOlpaVGQECA8eGHHxqGYRitW7c25s2bZ79eXl5uXHTRRfb3MgzDuPHGG42JEycahmEYGRkZhiQjOTn5nHF+8sknhiTj5MmT9nMlJSVG06ZNjR07dji0HT16tHHHHXcYhmEYjz32mNG5c2eH69OmTTvrXr8myVi3bp3T6/Pnzzd69uxpf/3kk08a3t7exg8//GA/98EHHxheXl7GiRMnDMMwjEsvvdRYu3atw32eeuopIzo62jAMw8jMzDQkGZ9//rnT9wVQt5gzgEZrw4YNat68ucrLy2Wz2XTnnXdq5syZ9utdu3Z1mCfwxRdf6PDhwwoMDHS4T0lJib799lsVFBToxIkTDo9t9vHxUa9evc4aKqiSnp4ub29v3XjjjdWO+/Dhwzp9+rRuuukmh/NlZWW68sorJUkHDx486/HR0dHR1X6PKm+++aaSkpL07bffqqioSBUVFQoKCnJo06ZNG1144YUO72Oz2ZSRkaHAwEB9++23Gj16tMaMGWNvU1FRIavV6nI8AOoGyQAarb59+2rZsmXy9fVVRESEfHwcf92bNWvm8LqoqEg9e/bUmjVrzrrXBRdccF4xBAQEuNynqKhIkvTee+85fAlLZ+ZBeEpqaqri4uI0a9YsxcbGymq16o033tBzzz3ncqyvvPLKWcmJt7e3x2IFULNIBtBoNWvWTO3bt692+6uuukpvvvmmQkNDz/rruErr1q21c+dO9e7dW9KZv4DT0tJ01VVXnbN9165dZbPZtHXrVsXExJx1vaoyUVlZaT/XuXNn+fn56ejRo04rCp06dbJPhqzy2Wef/f6H/IUdO3aobdu2evzxx+3njhw5cla7o0eP6vjx44qIiLC/j5eXlzp06KCwsDBFRETou+++U1xcnEvvD6D+YAIh8F9xcXFq1aqVhgwZom3btikzM1NbtmzRgw8+qB9++EGSNHHiRD3zzDNav369vv76az3wwAO/uUfAxRdfrPj4eN17771av369/Z5vvfWWJKlt27ayWCzasGGDfvzxRxUVFSkwMFAPP/ywJk+erFWrVunbb7/V3r17tWTJEvukvPvvv1+HDh3S1KlTlZGRobVr12rlypUufd7LLrtMR48e1RtvvKFvv/1WSUlJ55wM6e/vr/j4eH3xxRfatm2bHnzwQd1+++0KDw+XJM2aNUuJiYlKSkrSN998o3379mnFihVauHChS/EAqDskA8B/NW3aVCkpKWrTpo2GDRumTp06afTo0SopKbFXCh566CGNHDlS8fHxio6OVmBgoG699dbfvO+yZct022236YEHHlDHjh01ZswYFRcXS5IuvPBCzZo1S48++qjCwsKUkJAgSXrqqac0ffp0JSYmqlOnThowYIDee+89tWvXTtKZcfx//etfWr9+vbp3767ly5dr7ty5Ln3eW265RZMnT1ZCQoJ69OihHTt2aPr06We1a9++vYYNG6ZBgwapf//+6tatm8PSwfvuu0+vvvqqVqxYoa5du+rGG2/UypUr7bECqP8shrOZTwAAwBSoDAAAYHIkAwAAmBzJAAAAJkcyAACAyZEMAABgciQDAACYHMkAAAAmRzIAAIDJkQwAAGByJAMAAJgcyQAAACZHMgAAgMn9fzlOeKuoUyADAAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>It appears that the model scored on f-score performs the best for this set of data and hyperparameters. Additional changes can probably be made to improve the model performance even more. Different scoring parameters can be used in the grid search CV as per the problem requirement but we were definitely able to mitigate some of the bias from the imbalanced dataset and train our model to predict minority classes better.</p>

</div>
</div>
</body>







</html>
