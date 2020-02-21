# The 25 most recommended startup books of all-time.

There are countless lists on the internet claiming to be **the** list of must-read startup books and it seemed that all those lists always recommended that same books minus two or three odd choices.


I wanted to find out what were the most recommended books about startups, and so I've made this. I've compiled more than **208 lists** and almost **4,000** recommendations found on the internet. To my knowledge, this is the most complete list of its kind on the subject.

*Disclaimer: I spent countless hours on this article so I've decided to put Amazon affiliation links to see if those kinds of detailed articles could be a viable source of revenue, ... or not 🤷‍♂️.*

If you want to jump right on the results go take a look below at the [full results](#the-25-most-recommended-startup-books-of-alltime). If you want to learn about the methodology, bear with me.

## Methodology:

I've simply asked Google for a few queries like "Best Startup Books", "Best entrepreneur books" and other variations of it. I have then scrapped all those pages (using ScrapingBee, a web scraping API I'm working on).

I've deduplicated the links and ended up with nearly 300 links. Using the title of the pages I was also able to quickly discards:

- list focussed on one particular editor
- list focussed on one particular topic (i.e "Best Book for Crypto Entrepreneur")
- list focussed on free books
- Quora and Reddit threads

I ended up with 254 HTML files. I went on opening all the files on my browser, open my chrome inspector, found and wrote the CSS selector matching book titles in the article. This took me around 2hours, almost 30 seconds per page. 

This also allowed me to discard even more nonrelevant pages. 

At this moment I had this big JSON file referencing the HTML page previously scrapped, and a CSS selector.

![](https://www.daolf.com/images/book_list/rules.png)

Using Python with Beautiful soup, I've extracted every text inside DOM elements that matched the CSS selector. I ended up with a huge list of books, not usable without some post-processing.

![](https://www.daolf.com/images/book_list/links.png)

To find the most quoted startup books I needed to normalize my results. As a matter of fact, a book like "7 habits of highly effective people" appeared on my results using 3 different titles:

- 7 habits of highly effective people
- Seven habits of highly effective people
- 7 habits for highly for effective people

This plus all the different variation like "{title} by {author}" or "{title} - {author}" made this task a bit tricky.

I ended up doing it using this simple custom Python function:
```python
def clean_link(link):
    link = link.encode().decode('ascii', errors='ignore')
    link = link.replace("'", '')
    link = link.lower()
    link = ' '.join([w for w in link.split(' ') if w not in ['the', 'a']])
    link = link.split('by')[0]
    link = link.split(':')[0]
    link = link.split('(')[0]
    link = ' '.join(link.split())
    link = link.replace('-', '_')
    link = ''.join([c for c in link if c.isalpha() or c == '_' or c == ' '])
    link = link.strip()
    link = link.replace(' ', '_')
    link = ''.join([c for c in link if c.isalpha() or c == '_'])
    return link
```
 and quite a bit of manual cleaning.

My list now looked like this:

![](https://www.daolf.com/images/book_list/clean_links.png)

From there it was easy to compute the most recommended books. You can find all the data used to process this list on this [repo](https://github.com/daolf/Most-recommended-startup-books). Now let's look at the list:


# The 25 most recommended startup books of all-time.

Details about the methodology available [here](https://www.daolf.com/posts/best-startup-books/)

### 25. [Delivering Happiness: A Path to Profits, Passion, and Purpose](https://amzn.to/37rgeZH) by Tony Hsieh (7.6% recommended)
    
![](https://www.daolf.com/images/book_list/25.jpg#center)

"In Delivering Happiness, Zappos CEO Tony Hsieh shares the different lessons he has learned in business and life, from starting a worm farm to running a pizza business, through LinkExchange, Zappos, and more. Fast-paced and down-to-earth, Deliverin Happiness shows how a very different kind of corporate culture is a powerful model for achieving success-and how by concentrating on the happiness of those around you, you can dramatically increase your own." [Amazon.com](https://amzn.to/37rgeZH)

### 24. [Shoe Dog: A Memoir by the Creator of Nike](https://amzn.to/2uEd9s8) by Phil Knight (7.6% recommended)
    
![](https://www.daolf.com/images/book_list/24.jpg#center)

"Knight details the many risks and daunting setbacks that stood between him and his dream - along with his early triumphs. Above all, he recalls the formative relationships with his first partners and employees, a ragtag group of misfits and seekers who became a tight-knit band of brothers. Together, harnessing the transcendent power of a shared mission and a deep belief in the spirit of sport, they built a brand that changed everything." [Amazon.com](https://amzn.to/2uEd9s8)

### 23. [Purple Cow: Transform Your Business by Being Remarkable](https://amzn.to/2OZFUq6) by Seth Godin (8.1% recommended)
    
![](https://www.daolf.com/images/book_list/23.jpg#center)

"You're either a Purple Cow or you're not. You're either remarkable or invisible. Make your choice. What do Apple, Starbucks, Dyson and Pret a Manger have in common? How do they achieve spectacular growth, leaving behind former tried-and-true brands to gasp their last? The old checklist of P's used by marketers - Pricing, Promotion, Publicity - aren't working anymore. The golden age of advertising is over. It's time to add a new P - the Purple Cow."Purple Cow" describes something phenomenal, something counterintuitive and exciting and flat-out unbelievable. In his new bestseller, Seth Godin urges you to put a Purple Cow into everything you build, and everything you do, to create something truly noticeable. It's a manifesto for anyone who wants to help create products and services that are worth marketing in the first place." [Amazon.com](https://amzn.to/2OZFUq6)

### 22. [Outliers: The Story of Success](https://amzn.to/31Xvexc) by Malcolm Gladwell (8.1% recommended)
    
![](https://www.daolf.com/images/book_list/22.jpg#center)

"In this stunning new book, Malcolm Gladwell takes us on an intellectual journey through the world of "outliers"--the best and the brightest, the most famous and the most successful. He asks the question: what makes high-achievers different? 

His answer is that we pay too much attention to what successful people are like, and too little attention to where they are from: that is, their culture, their family, their generation, and the idiosyncratic experiences of their upbringing. Along the way he explains the secrets of software billionaires, what it takes to be a great soccer player, why Asians are good at math, and what made the Beatles the greatest rock band." [Amazon.com](https://amzn.to/31Xvexc)

### 21. [The Power of Habit: Why We Do What We Do in Life and Business](https://amzn.to/2wnfW9D) by Charles Duhigg (8.1% recommended)
    
![](https://www.daolf.com/images/book_list/21.jpg#center)

"In The Power of Habit, award-winning business reporter Charles Duhigg takes us to the thrilling edge of scientific discoveries that explain why habits exist and how they can be changed. Distilling vast amounts of information into engrossing narratives that take us from the boardrooms of Procter & Gamble to the sidelines of the NFL to the front lines of the civil rights movement, Duhigg presents a whole new understanding of human nature and its potential. At its core, The Power of Habit contains an exhilarating argument: The key to exercising regularly, losing weight, being more productive, and achieving success is understanding how habits work. As Duhigg shows, by harnessing this new science, we can transform our businesses, our communities, and our lives." [Amazon.com](https://amzn.to/2wnfW9D)

### 20. [Founders at Work: Stories of Startups' Early Days](https://amzn.to/37wUFH4) by  Jessica Livingston ( 8.6% recommended)
    
![](https://www.daolf.com/images/book_list/20.jpg#center)

"For would-be entrepreneurs, innovation managers or just anyone fascinated by the special chemistry and drive that created some of the best technology companies in the world, this book offers both wisdom and engaging insights straight from the source. FaW is a collection of interviews with founders of famous technology companies about what happened in the very earliest days." [Amazon.com](https://amzn.to/37wUFH4)

### 19. [Hooked: A Guide to Building Habit-Forming Products](https://amzn.to/2HoRPcz) by Nir Eyal (8.6% recommended)
    
![](https://www.daolf.com/images/book_list/19.jpg#center)

""Hooked" presents a simple, yet very useful model to channel your thoughts when building a product you want to get in the hands of millions. It's quick to read (only 140 pages), to-the-point and made a world of difference to our concept&design challenges. We used it a lot to model the behavior of our users and figure out specific areas we missed and needed to focus on in order to get engagement.

Another great value of the book is the in-depth analysis of the hooks we are subject to every day (in Twitter, Facebook, Pinterest, Instagram etc). As you go around the everyday loop you know so well from the user perspective, you see in a structured way the other side of the coin. The side of the people who know how to design behavior patterns and make others tick." [Amazon.com](https://amzn.to/2HoRPcz)

### 18. [The Innovator's Dilemma: When New Technologies Cause Great Firms to Fail](https://amzn.to/2SueY3F) by Clayton M. Christensen (9.1% recommended)
    
![](https://www.daolf.com/images/book_list/18.jpg#center)

"Christensen explains why most companies miss out on new waves of innovation. No matter the industry, he says, a successful company with established products will get pushed aside unless managers know how and when to abandon traditional business practices.

Offering both successes and failures from leading companies as a guide, The Innovator’s Dilemma gives you a set of rules for capitalizing on the phenomenon of disruptive innovation." [Amazon.com](https://amzn.to/2SueY3F)

### 17. [Art of the Start 2.0: The Time-Tested, Battle-Hardened Guide for Anyone Starting Anything](https://amzn.to/38y7CSr) by Guy Kawasaki (9.1% recommended)
    
![](https://www.daolf.com/images/book_list/17.jpg#center)

"In The Art of the Start, Guy Kawasaki brings two decades of experience as one of business’s most original and irreverent strategists to offer the essential guide for anyone starting anything, from a multinational corporation to a church group. At Apple in the 1980s, he helped lead one of the great companies of the century, turning ordinary consumers into evangelists. As founder and CEO of Garage Technology Ventures, a venture capital firm, he has field-tested his ideas with dozens of newly hatched companies. And as the author of bestselling business books and articles, he has advised thousands of people who are making their startup dreams real." [Amazon.com](https://amzn.to/38y7CSr)

### 16. [Tools of Titans: The Tactics, Routines, and Habits of Billionaires, Icons, and World-Class Performers](https://amzn.to/323obmP) by Tim Ferriss (9.1% recommended)
    
![](https://www.daolf.com/images/book_list/16.jpg#center)

"From the author:
 
“For the last two years, I’ve interviewed more than 200 world-class performers for my podcast, The Tim Ferriss Show. The guests range from super celebs (Jamie Foxx, Arnold Schwarzenegger, etc.) and athletes (icons of powerlifting, gymnastics, surfing, etc.) to legendary Special Operations commanders and black-market biochemists. For most of my guests, it’s the first time they’ve agreed to a two-to-three-hour interview. This unusual depth has helped make The Tim Ferriss Show the first business/interview podcast to pass 100 million downloads." [Amazon.com](https://amzn.to/323obmP)

### 15. [Influence: Science and Practice](https://amzn.to/31VeNBA) by Robert B. Cialdini (9.6% recommended)
    
![](https://www.daolf.com/images/book_list/15.jpg#center)

"Written in a narrative style combined with scholarly research, Cialdini combines evidence from experimental work with the techniques and strategies he gathered while working as a salesperson, fundraiser, advertiser, and in other positions inside organizations that commonly use compliance tactics to get us to say “yes.” Widely used in classes, as well as sold to people operating successfully in the business world, the eagerly awaited revision of Influence reminds the reader of the power of persuasion." [Amazon.com](https://amzn.to/31VeNBA)

### 14. [Traction](https://amzn.to/31XH4aJ) by  Gabriel Weinberg and Justin Mares (9.6% recommended)
    
![](https://www.daolf.com/images/book_list/14.jpg#center)

"Traction will teach you the nineteen channels you can use to build a customer base, and how to pick the right ones for your business. It draws on inter-views with more than forty successful founders, including Jimmy Wales (Wikipedia), Alexis Ohanian (reddit), Paul English (Kayak), and Dharmesh Shah (HubSpot). You’ll learn, for example, how to:
 
- Find and use offline ads and other channels your competitors probably aren’t using
- Get targeted media coverage that will help you reach more customers
- Boost the effectiveness of your email marketing campaigns by automating staggered sets of prompts and updates
- Improve your search engine rankings and advertising through online tools and research"
[Amazon.com](https://amzn.to/31XH4aJ)

### 13. [Rich Dad Poor Dad](https://amzn.to/2wf6Knn) by Robert T. Kiyosaki (12.9% recommended)
    
![](https://www.daolf.com/images/book_list/13.jpg#center)

"Rich Dad Poor Dad is Robert's story of growing up with two dads — his real father and the father of his best friend, his rich dad — and the ways in which both men shaped his thoughts about money and investing. The book explodes the myth that you need to earn a high income to be rich and explains the difference between working for money and having your money work for you." [Amazon.com](https://amzn.to/2wf6Knn)

### 12. [The 7 Habits of Highly Effective People](https://amzn.to/2SvHtyb) by Stephen R. Covey (12.9% recommended)
    
![](https://www.daolf.com/images/book_list/12.jpg#center)

"One of the most inspiring and impactful books ever written, The 7 Habits of Highly Effective People has captivated readers for 25 years. It has transformed the lives of presidents and CEOs, educators and parents—in short, millions of people of all ages and occupations across the world. This twenty-fifth anniversary edition of Stephen Covey’s cherished classic commemorates his timeless wisdom, and encourages us to live a life of great and enduring purpose." [Amazon.com](https://amzn.to/2SvHtyb)

### 11. [Rework](https://amzn.to/2SufFKn) by Jason Fried and David Heinemeier Hansson (14% recommended)
    
![](https://www.daolf.com/images/book_list/11.jpg#center)

"Most business books give you the same old advice: Write a business plan, study the competition, seek investors, yadda yadda. If you're looking for a book like that, put this one back on the shelf.

Read it and you'll know why plans are actually harmful, why you don't need outside investors, and why you're better off ignoring the competition. The truth is, you need less than you think. You don't need to be a workaholic. You don't need to staff up. You don't need to waste time on paperwork or meetings. You don't even need an office. Those are all just excuses. 

What you really need to do is stop talking and start working. This book shows you the way. You'll learn how to be more productive, how to get exposure without breaking the bank, and tons more counterintuitive ideas that will inspire and provoke you.

With its straightforward language and easy-is-better approach, Rework is the perfect playbook for anyone who’s ever dreamed of doing it on their own. Hardcore entrepreneurs, small-business owners, people stuck in day jobs they hate, victims of "downsizing," and artists who don’t want to starve anymore will all find valuable guidance in these pages." [Amazon.com](https://amzn.to/2SufFKn)

### 10. [Start with Why](https://amzn.to/2wikE8l) by Simon Sinek (14.4% recommended)
    
![](https://www.daolf.com/images/book_list/10.jpg#center)

"Sinek starts with a fundamental question: Why are some people and organizations more innovative, more influential, and more profitable than others? Why do some command greater loyalty from customers and employees alike? Even among the successful, why are so few able to repeat their success over and over?
 
People like Martin Luther King Jr., Steve Jobs, and the Wright Brothers had little in common, but they all started with WHY. They realized that people won't truly buy into a product, service, movement, or idea until they understand the WHY behind it. 
 
START WITH WHY shows that the leaders who've had the greatest influence in the world all think, act, and communicate the same way -- and it's the opposite of what everyone else does. Sinek calls this powerful idea The Golden Circle, and it provides a framework upon which organizations can be built, movements can be led, and people can be inspired. And it all starts with WHY." [Amazon.com](https://amzn.to/2wikE8l)

### 9. [Think and Grow Rich](https://amzn.to/39DlcUN) by Napoleon Hill (14.4% recommended)
    
![](https://www.daolf.com/images/book_list/9.jpg#center)

"Think and Grow Rich has been called the "Granddaddy of All Motivational Literature." It was the first book to boldly ask, "What makes a winner?" The man who asked and listened for the answer, Napoleon Hill, is now counted in the top ranks of the world's winners himself.
The most famous of all teachers of success spent "a fortune and the better part of a lifetime of effort" to produce the "Law of Success" philosophy that forms the basis of his books and that is so powerfully summarized in this one.

In the original Think and Grow Rich, published in 1937, Hill draws on stories of Andrew Carnegie, Thomas Edison, Henry Ford, and other millionaires of his generation to illustrate his principles. In the updated version, Arthur R. Pell, Ph.D., a nationally known author, lecturer, and consultant in human resources management and an expert in applying Hill's thought, deftly interweaves anecdotes of how contemporary millionaires and billionaires, such as Bill Gates, Mary Kay Ash, Dave Thomas, and Sir John Templeton, achieved their wealth. Outmoded or arcane terminology and examples are faithfully refreshed to preclude any stumbling blocks to a new generation of readers." [Amazon.com](https://amzn.to/39DlcUN)

### 8. [Good to Great: Why Some Companies Make the Leap and Others Don't](https://amzn.to/37wvV1U) by Jim Collins  (14.9% recommended)
    
![](https://www.daolf.com/images/book_list/8.jpg#center)

"Five years ago, Jim Collins asked the question, "Can a good company become a great company and if so, how?" In Good to Great Collins, the author of Built to Last, concludes that it is possible, but finds there are no silver bullets. Collins and his team of researchers began their quest by sorting through a list of 1,435 companies, looking for those that made substantial improvements in their performance over time. They finally settled on 11--including Fannie Mae, Gillette, Walgreens, and Wells Fargo--and discovered common traits that challenged many of the conventional notions of corporate success. Making the transition from good to great doesn't require a high-profile CEO, the latest technology, innovative change management, or even a fine-tuned business strategy. At the heart of those rare and truly great companies was a corporate culture that rigorously found and promoted disciplined people to think and act in a disciplined manner. Peppered with dozens of stories and examples from the great and not so great, the book offers a well-reasoned road map to excellence that any organization would do well to consider. Like Built to Last, Good to Great is one of those books that managers and CEOs will be reading and rereading for years to come." [Amazon.com](https://amzn.to/37wvV1U)

### 7. [The E-Myth Revisited: Why Most Small Businesses Don't Work and What to Do About It ](https://amzn.to/39zZZuS) by Michael E. Gerber  (15.3% recommended)
    
![](https://www.daolf.com/images/book_list/7.jpg#center)

"An instant classic, this revised and updated edition of the phenomenal bestseller dispels the myths about starting your own business. Small business consultant and author Michael E. Gerber, with sharp insight gained from years of experience, points out how common assumptions, expectations, and even technical expertise can get in the way of running a successful business.

Gerber walks you through the steps in the life of a business—from entrepreneurial infancy through adolescent growing pains to the mature entrepreneurial perspective: the guiding light of all businesses that succeed—and shows how to apply the lessons of franchising to any business, whether or not it is a franchise. Most importantly, Gerber draws the vital, often overlooked distinction between working on your business and working in your business." [Amazon.com](https://amzn.to/39zZZuS)

### 6. [The 4-Hour Workweek](https://amzn.to/3bDW7La) by Timothy Ferriss (15.8% recommended)
    
![](https://www.daolf.com/images/book_list/6.jpg#center)

"Forget the old concept of retirement and the rest of the deferred-life plan–there is no need to wait and every reason not to, especially in unpredictable economic times. Whether your dream is escaping the rat race, experiencing high-end world travel, or earning a monthly five-figure income with zero management, The 4-Hour Workweek is the blueprint." [Amazon.com](https://amzn.to/3bDW7La)

### 5. [How To Win Friends and Influence People](https://amzn.to/31WyKrP) by Dale Carnegie (22.5% recommended)
    
![](https://www.daolf.com/images/book_list/5.jpg#center)

"Dale Carnegie’s rock-solid, time-tested advice has carried countless people up the ladder of success in their business and personal lives. One of the most groundbreaking and timeless bestsellers of all time, How to Win Friends & Influence People will teach you:

- Six ways to make people like you

- Twelve ways to win people to your way of thinking

- Nine ways to change people without arousing resentment

And much more! Achieve your maximum potential—a must-read for the twenty-first century with more than 15 million copies sold!" [Amazon.com](https://amzn.to/31WyKrP)

### 4. [The $100 Startup: Reinvent the Way You Make a Living, Do What You Love, and Create a New Future](https://amzn.to/2SvDPEz) by Chris Guillebeau (24% recommended)
    
![](https://www.daolf.com/images/book_list/4.jpg#center)

"Still in his early thirties, Chris is on the verge of completing a tour of every country on earth – he’s already visited more than 175 nations – and yet he’s never held a “real job” or earned a regular paycheck.  Rather, he has a special genius for turning ideas into income, and he uses what he earns both to support his life of adventure and to give back. 
 
There are many others like Chris – those who’ve found ways to opt out of traditional employment and create the time and income to pursue what they find meaningful.  Sometimes, achieving that perfect blend of passion and income doesn’t depend on shelving what you currently do.  You can start small with your venture, committing little time or money, and wait to take the real plunge when you're sure it's successful." [Amazon.com](https://amzn.to/2SvDPEz)

### 3. [The Hard Thing About Hard Things](https://amzn.to/2StUZC9) by Ben Horowitz (24.5% recommended)
    
![](https://www.daolf.com/images/book_list/3.jpg#center)

"Ben Horowitz, cofounder of Andreessen Horowitz and one of Silicon Valley's most respected and experienced entrepreneurs, offers essential advice on building and running a startup—practical wisdom for managing the toughest problems business school doesn’t cover, based on his popular ben’s blog.

While many people talk about how great it is to start a business, very few are honest about how difficult it is to run one. Ben Horowitz analyzes the problems that confront leaders every day, sharing the insights he’s gained developing, managing, selling, buying, investing in, and supervising technology companies. A lifelong rap fanatic, he amplifies business lessons with lyrics from his favorite songs, telling it straight about everything from firing friends to poaching competitors, cultivating and sustaining a CEO mentality to knowing the right time to cash in.

Filled with his trademark humor and straight talk, The Hard Thing About Hard Things is invaluable for veteran entrepreneurs as well as those aspiring to their own new ventures, drawing from Horowitz's personal and often humbling experiences." [Amazon.com](https://amzn.to/2StUZC9)

### 2. [Zero to One](https://amzn.to/3bIB1Lw) by Peter Thiel (29.3% recommended)
    
![](https://www.daolf.com/images/book_list/2.jpg#center)

"The great secret of our time is that there are still uncharted frontiers to explore and new inventions to create. In Zero to One, legendary entrepreneur and investor Peter Thiel shows how we can find singular ways to create those new things.

Thiel begins with the contrarian premise that we live in an age of technological stagnation, even if we’re too distracted by shiny mobile devices to notice. Information technology has improved rapidly, but there is no reason why progress should be limited to computers or Silicon Valley. Progress can be achieved in any industry or area of business. It comes from the most important skill that every leader must master: learning to think for yourself.

Doing what someone else already knows how to do takes the world from 1 to n, adding more of something familiar. But when you do something new, you go from 0 to 1. The next Bill Gates will not build an operating system. The next Larry Page or Sergey Brin won’t make a search engine. Tomorrow’s champions will not win by competing ruthlessly in today’s marketplace. They will escape competition altogether, because their businesses will be unique.

Zero to One presents at once an optimistic view of the future of progress in America and a new way of thinking about innovation: it starts by learning to ask the questions that lead you to find value in unexpected places." [Amazon.com](https://amzn.to/3bIB1Lw)

### 1. [The Lean Startup](https://amzn.to/3bBJtwp) by Eric Ries (44.7% recommended)
    
![](https://www.daolf.com/images/book_list/1.jpg#center)

"Eric Ries defines a startup as an organization dedicated to creating something new under conditions of extreme uncertainty. This is just as true for one person in a garage or a group of seasoned professionals in a Fortune 500 boardroom. What they have in common is a mission to penetrate that fog of uncertainty to discover a successful path to a sustainable business.

The Lean Startup approach fosters companies that are both more capital efficient and that leverage human creativity more effectively. Inspired by lessons from lean manufacturing, it relies on “validated learning,” rapid scientific experimentation, as well as a number of counter-intuitive practices that shorten product development cycles, measure actual progress without resorting to vanity metrics, and learn what customers really want. It enables a company to shift directions with agility, altering plans inch by inch, minute by minute.

Rather than wasting time creating elaborate business plans, The Lean Startup offers entrepreneurs—in companies of all sizes—a way to test their vision continuously, to adapt and adjust before it’s too late. Ries provides a scientific approach to creating and managing successful startups in a age when companies need to innovate more than ever." [Amazon.com](https://amzn.to/3bBJtwp)


## Conclusion

Although the order might suprise some, by definition, most of you must have heard of these book already.

A few additional things I learned making this list: 
- Tim Ferriss is the only author with several books in the list.
- The Bible was quoted one time
- The [Steve Jobs biography](https://amzn.to/2SKalRW) by Walter Isaacson is the most quoted biography, being recommended by 6% of the article.

I hope you enjoyed this article. 

*Originally posted on [daolf.com](https://www.daolf.com/posts/best-startup-books/)*
