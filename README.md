# Accessible Accordions

Accessible accordion jQuery plug-in.

DEMO: http://scottaohara.github.io/accessible_accordions/

Based on: https://www.w3.org/TR/wai-aria-practices/#accordion


## Keyboard Controls

When focus on the accordion tabs:

  * <kbd>Up</kbd> & <kbd>Left</kbd> move focus to previous tabs

  * <kbd>Down</kbd> & <kbd>Right</kbd> move focus to next tabs

  * <kbd>Home</kbd> moves focus to the first accordion tab

  * <kbd>End</kbd> moves focus to the last accordion tab

  * <kbd>Space</kbd> or <kbd>Enter</kbd> open/close the tab's associated panel

When focus is in an accordion panel:

  * <kbd>Ctrl</kbd> + <kbd>Up</kbd> moves focus to its associated accordion tab

  * <kbd>Ctrl</kbd> + <kbd>Page Up</kbd> moves focus to the previous tab of the currently active tab/panel.

  * <kbd>Ctrl</kbd> + <kbd>Page Down</kbd> moves focus to the next tab after the currently active tab/panel.


__Take Note:__

In some browsers (namely FireFox), <kbd>Ctrl</kbd> + <kbd>Page Down</kbd> or <kbd>Page Up</kbd> is used by the browser to move between other browser tabs.


## Minimum Required Mark-up

```html
<div class="accordion" data-action="is-accordion" id="accGen">

  <!--
    The Tab will be generated by the 'data-tab-label' value.
  -->
  <div class="accordion__panel" data-tab-label="My Title here">
    ...
  </div>


  <!--
    The Tab will be generated by converting the <h2> to a <button>
  -->
  <h2>
    Tab Heading
  </h2>
  <div class="accordion__panel">
    ...
  </div>

  <!--
    As there is no <h#> or 'data-tab-label' attribute, a
    <button> will be generated with the label "Tab #", where
    # = the number of the tab in the DOM order. This being
    the 3rd tab in the DOM order, so the label would be "Tab 3"
  -->
  <div class="accordion__panel">
    ...
  </div>
</div>
```

If you have complete control over your mark-up, and want to include a completely CSS powered solution for instances where JavaScript may not be available, you can implement the following:

```html
<div class="accordion" data-action="is-accordion" id="otherEx">
  <a href="#p1" class="accordion__trigger">
    Tab 1
  </a>
  <div class="accordion__panel" id="p1">
    ...
  </div>

  <a href="#p2" class="accordion__trigger">
    Tab 2
  </a>
  <div class="accordion__panel" id="p2">
    ...
  </div>
</div>
```


## Options

Add the following data attributes to their respected element to extend the accordion setup process:


  __container__

    * data-showall="true"

      show all panels by default

    * data-multi-open="true"

      individual accordion can have multiple tabs open at once


  __panel__

    * data-showbydefault="true"

      show individual panel by default

    * data-tab-label="Your Label Here"

      set the text for the auto generated tab/trigger for
      this panel (only if the panel does not have a
      preceding heading element)
