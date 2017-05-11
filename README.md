# moduleEdit
/* Magic Mirror Config
 *
 * By Michael Teeuw http://michaelteeuw.nl
 * MIT Licensed.
 */

var config = {
	port: 8080,
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1"], // Set [] to allow all IP addresses.

	language: "en",
	timeFormat: 24,
	units: "imperial",

	modules: [
		{
			module: "alert",
			config: {
				effect: "bouncyflip",
			}
		},
		{
			module: "clock",
			position: "top_left"
			config: {
				clockBold: "true"
				timezone: "America/California"
			}
		},
		{
			module: "calendar",
			header: "LIFE EVENTS",
			position: "top_left",
			config: {
				maximumEntries: 5
				timeFormat: absolute
				calendars: [
					{
						url: "webcal://www.calendarlabs.com/templates/ical/US-Holidays.ics"
					},
					{
						url: 
"https://calendar.google.com/calendar/ical/kescobar%40callutheran.edu/public/basic.ics"
					}
				]
			}
		},
    	{
			module: "newsfeed",
			position: "bottom_bar",
			config: {
				feeds: [
					{
						title: "LA Times National",
						url: "http://www.latimes.com/nation/rss2.0.xml"
						title: "LA Times World",
						url: "http://www.latimes.com/world/rss2.0.xml
					}
				],
				showSourceTitle: true,
				showPublishDate: true
			}
		},
		{
			module: "compliments",
			position: "lower_third"
			config: {
				compliments: {
					anytime: [
						"Hello there, beautiful"
					],
					morning: [
						"Good morning, gorgeous!"
						"Enjoy your day!"
						"How was your sleep?"
					],
					afternoon: [
						"You look fantastic!"
						"Lookin' good today!"
						"Have you done any good today?"
					],
					evening: [
						"Wow, you look phenom!"
						"You look nice!"
						"Have a great night!"
					]
				}
			}
		},
		{
			module: "currentweather",
			position: "top_right",
			config: {
				location: "Los Angeles, US", //this will be overrode by the locationID, because I filled it out
				locationID: "3882428",  //ID from http://www.openweathermap.org/help/city_list.txt
				appid: "8da092a3f1f616c538036c8364946c55"
				degreeLabel: true
			}
		},
		{
			module: "weatherforecast",
			position: "top_right",
			header: "Weather Forecast",
			config: {
				location: "Los Angeles, US",
				locationID: "3882428",  //ID from http://www.openweathermap.org/help/city_list.txt
				appid: "8da092a3f1f616c538036c8364946c55"
				showRainAmount: true
				colored: true
			}
		},
		{
			module: 'MMM-Astrology',
			position: 'top-right',
			config: {
				starSign: "Gemini",
				hScope: "daily"
				maxWidth: "350",
		},
	]

};

/*************** DO NOT EDIT THE LINE BELOW ***************/
if (typeof module !== "undefined") {module.exports = config;}
