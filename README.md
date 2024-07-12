# Codedex-Summer-Hackathon---Track-2
Submission for the Codedex Summer Hackathon 2024 for Track 2 Web Build
Code I wrote in Wix 

// Velo API Reference: https://www.wix.com/velo/reference/api-overview/introduction

$w.onReady(function () {

	// Write your Javascript code here using the Velo framework API

	// Print hello world:
	// console.log("Hello world!");

	// Call functions on page elements, e.g.:
	// $w("#button1").label = "Click me!";

	// Click "Run", or Preview your site, to execute your code

	
});

/**
*	Adds an event handler that runs when the element is clicked.
	[Read more](https://www.wix.com/corvid/reference/$w.ClickableMixin.html#onClick)
*	 @param {$w.MouseEvent} event
*/

let mapVisible = false;

export function mapSign_click(event) {
    // Toggle the visibility of the map iframe when the image is clicked
    mapVisible = !mapVisible;
    if (mapVisible) {
        $w('#mapPin').show();
    } else {
        $w('#mapPin').hide();
    }
}




/**
*	Adds an event handler that runs when the element is clicked.
	[Read more](https://www.wix.com/corvid/reference/$w.ClickableMixin.html#onClick)
*	 @param {$w.MouseEvent} event
*/

let eventBoxVisible = false;

export function calendar_click(event) {
	// This function was added from the Properties & Events panel. To learn more, visit http://wix.to/UcBnC-4
	// Add your code for this event here: 
	eventBoxVisible = !eventBoxVisible;
    if (eventBoxVisible) {
        $w('#eventBox').show();
    } else {
        $w('#eventBox').hide();
    }
}

// Function to add event to user's calendar



/**
*	Adds an event handler that runs when the element is clicked.
	[Read more](https://www.wix.com/corvid/reference/$w.ClickableMixin.html#onClick)
*	 @param {$w.MouseEvent} event
*/
export function addEventButton_click(event) {
	// This function was added from the Properties & Events panel. To learn more, visit http://wix.to/UcBnC-4
	// Add your code for this event here: 

	// Create the calendar event details
    const eventDetails = {
        title: "liLCea Stoop Sale",
        location: "2nd Pl and Court St, Caroll Gardens, Brooklyn",
        description: "A selection of good quality, tasteful and awesome things!",
        startTime: new Date("2024-08-08T10:00:00"),
        endTime: new Date("2024-08-08T18:00:00")
    };

    // Create the URL for the calendar event
    const calendarUrl = `https://www.google.com/calendar/render?action=TEMPLATE&text=${encodeURIComponent(eventDetails.title)}&dates=${eventDetails.startTime.toISOString().replace(/-|:|\.\d+/g, '')}/${eventDetails.endTime.toISOString().replace(/-|:|\.\d+/g, '')}&details=${encodeURIComponent(eventDetails.description)}&location=${encodeURIComponent(eventDetails.location)}`;

     // Open the calendar URL in a new tab
    wixWindow.openURL(calendarUrl, '_blank');
}
