# guided-tours
## Guided tours for the platform

Edit tours.json to add, change, or remove tours.  Tour translations are stored in /nl/<lang>/.

## Tour.json Format
Each tour consists of a id (which must be unique) some criteria that specifies when it should be shown and an array of 1-4 panels.  

Each panel consists of an image, title, and body text.  All images must be 650x235 pixels, but can be jpg, png, or gif format.  The panels can have an optional call to action (cta) link with specified label and url.

### Details for each field

- id: A unique name for this tour.  Used to ensure this tour is not shown more than once.
- tourCriteria: Contains the criteria for when the tour should be shown
- urlRegex: A regular expression applied to the url path to determine if the tour should be shown.  If the tour should appear on all pages use `".*"`
- newUser: A boolean indicating if the tour should be shown to new users, false if it should be shown to existing users. (optional)
- suppressTours: An array of tour id's that should never be shown if this tour is viewed. (optional)
- tourPanels: An array of tour panels
- image: A url (relative recommended) to the image to be displayed for this panel
- title: The title for this panel
- body: The body text for this panel
- ctaText: The label for a link added to the end of the body text - typically used for learn more (optional)
- ctaURL: The url for the a link added to the end of the body text (optional, unless ctaText is used)


## Content guidance
Follow the conversational tone defined in Carbon http://carbondesignsystem.com/guidelines/content/general for the title and body. Leverage the approved action labels for the buttons and follow guidance in Carbon http://carbondesignsystem.com/components/button/usage.

## Suppressing Tours

If a tour should never appear on a particular set of pages, use the urlRegex attribute.  If a tour should not be shown if another tour was shown use the suppressTours attribute.  If a tour should not appear under certain conditions such as when guiding the user through a particular process, a url parameter `hideTours=true` can be set.
