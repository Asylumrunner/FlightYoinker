# FlightYoinker
Yoinks flight data based on predetermined sets of dates and flight routes

## Design
I fly a lot, and the (purposefully) arcane and unknowable dark science that is "figuring out when flights are cheap" is deeply annoying to me. So, I decided to build a scraper designed to pull flight information on my behalf, store it, send it to me, keep track of prices over time, and ideally, obtain enough data over time that I can build my own analytical models of flight prices.

### Aren't There Like 20 Apps That Do This Already?
Yes! Sorta.

There are a myriad of very good apps that let you track a specific flight over time and can even tell you when you should probably pull the trigger, which is rad! However, that's not quite how I fly. Instead, I have a set of dates that I know I'm probably going to be free, and a set of destinations I would like to go to, without any real inherent mappings between the two. Even seasonal considerations tend to not stop me (I've frozen my ass off in Canada in Winter, and sweat my ass off in Japan in Summer), so really what I'm looking to do here is find optimal mappings between this lists of destinations and dates.

Plus, hey, I'm a programmer, I like programming things.

### How This Works
The scraper pulls flight details by regularly searching a flight aggregator website, using Selenium to read and retrieve flight prices as I so need them.

The scraper pulls flight data for all destination/date pairs possible, storing all of the results in a database for further consumption later. This will be generated into an end of day report that is emailed out, but if any deals are particularly good, they'll be texted to me as soon as they are found.

