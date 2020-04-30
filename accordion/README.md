Responsive Accordion Accessibility Compliant

Below is the W3 description of an accordion and the requirements to meet accessibility.

An accordion is a vertically stacked set of interactive headings that each contain a title, content snippet, or thumbnail representing a section of content. The headings function as controls that enable users to reveal or hide their associated sections of content. Accordions are commonly used to reduce the need to scroll when presenting multiple sections of content on a single page.

Components of an Accordion

Header

Label for or thumbnail representing a section of content that also serves as a control for showing, and in some implementations, hiding the section of content.

Panel

Section of content associated with an accordion header.

In some accordions, there are additional elements that are always visible adjacent to the accordion header. For instance, a menubutton may accompany each accordion header to provide access to actions that apply to that section. And, in some cases, a snippet of the hidden content may also be visually persistent.

Keyboard Interaction

Enter or Space

When focus is on the accordion header for a collapsed panel, expands the associated panel. If the implementation allows only one panel to be expanded, and if another panel is expanded, collapses that panel.

When focus is on the accordion header for an expanded panel, collapses the panel if the implementation supports collapsing. Some implementations require one panel to be expanded at all times and allow only one panel to be expanded; so, they do not support a collapse function.

Tab 

Moves focus to the next focusable element; all focusable elements in the accordion are included in the page Tab sequence.

Shift + Tab

Moves focus to the previous focusable element; all focusable elements in the accordion are included in the page Tab sequence.

Down Arrow (Optional)I

If focus is on an accordion header, moves focus to the next accordion header. If focus is on the last accordion header, either does nothing or moves focus to the first accordion header.

Up Arrow (Optional)

If focus is on an accordion header, moves focus to the previous accordion header. If focus is on the first accordion header, either does nothing or moves focus to the last accordion header.

Home (Optional)

When focus is on an accordion header, moves focus to the first accordion header.

End (Optional)
When focus is on an accordion header, moves focus to the last accordion header.

WAI-ARIA Roles, States, and Properties

The title of each accordion header is contained in an element with role button.

Each accordion header button is wrapped in an element with role heading that has a value set for aria-level that is appropriate for the information architecture of the page.

If the native host language has an element with an implicit heading and aria-level, such as an HTML heading tag, a native host language element may be used.

The button element is the only element inside the heading element. That is, if there are other visually persistent elements, they are not included inside the heading element.

If the accordion panel associated with an accordion header is visible, the header button element has aria-expanded set to true. If the panel is not visible, aria-expanded is set to false.

The accordion header button element has aria-controls set to the ID of the element containing the accordion panel content.

If the accordion panel associated with an accordion header is visible, and if the accordion does not permit the panel to be collapsed, the header button element has aria-disabled set to true.

Optionally, each element that serves as a container for panel content has role region and aria-labelledby with a value that refers to the button that controls display of the panel.

Avoid using the region role in circumstances that create landmark region proliferation, e.g., in an accordion that contains more than approximately 6 panels that can be expanded at the same time.

Role region is especially helpful to the perception of structure by screen reader users when panels contain heading elements or a nested accordion.