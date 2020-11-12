# Simple-Instagram-Scraper
## A highly customizable Instagram Scraper based on Selenium.
v1.0.1

Due to latest Instagram blocking policy changes [Instagram Scraper](https://github.com/arc298/instagram-scraper) is temporarily not performing well.
I came up with my own scraping script to overcome repeated 429 http blocking errors by "behaving like a human". 
Use this juypter notebook to gain full control over your scraping!

## Idea
The main loop literally looks at every individual post, parses and saves the data and goes to the next one by clicking the small arrow.
It acts kinda human by pausing pretty randomely (long breaks and short breaks can be defined) and typing a comment now and then (but not confirming). 

## Break handling 
Short breaks are the ones between visualizing a post and going to the next one (random, i.e. 1-2 seconds).
Long breaks are randomely occuring longer breaks after every nth (+ a lot of randomness) iteration.

## Pause and resume 
You can pause (use jupyter's "interrupt" function) and resume (just reexecute the cell with the main loop) at any time. Just keep in mind that the browser must be kept open. 

## Error handling 
Instagram will sometimes display less posts after a while. If this occurs the script makes a break, goes back to the previous post and continues normally. If a single post cannot be visualized the post id will still be saved so can easily filter the dataframe after and add missing information.

## Benchmarks 
A quick trial went well for around 2k posts. Depending on your break settings a reasonable time in this case would be ~4 hours.

## To Do
- Disable caching! Otherwise fails after ~8k posts
- Improve error handling, i.e. after n non displayable posts do very long break
- More benchmarking to figure out ideal break duration and intervals
- Add a second login account when blocked completely 
- Add media download possibility
