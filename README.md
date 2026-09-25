# Should I Buy It?

## Original idea

**When someone enters the price of a non-essential purchase, how often they expect to use it, how long they have wanted it, and how much flexible money they have left, the experience should recommend whether to buy it, wait, or skip it—and explain why.**

The target user is a student or young adult who wants a quick pause before making an impulse purchase. 

## How to open it

1. Change the sample item, price, optional-spending budget, expected use, and waiting time.
2. Select “Check this purchase“ to receive an explained result.

## AI tool and selected prompts

I used Codex as a design and coding partner. Important prompts and decisions included:

“When someone enter the non-essential products they want, the experience should tell them whether buy/not buy/wait".

“Build ‘Should I Buy It?’ tool based on price, expected use, waiting time, and the user’s remaining optional-spending budget. Keep it to one main interaction and explain the result.”

“Make the result feel like a decision receipt. Do not hide the reasoning behind a single score.”

AI helped turn the idea into HTML, CSS, JavaScript, and an initial scoring model. I still had to give my own ideas, decide which questions were useful, which factors should have more weight, and whether the result should be framed as a command or as a prompt for reflection.

## Reflection draft

Rather than making a program that simply tells me whether or not to buy something, I wanted to create a tool that helps me pause and think before making an impulse purchase. That part worked the way I expected. The user enters the price, how much spending money they have left, how often they think they will use the item, and how long they have wanted it. The page then gives a BUY, WAIT, or SKIP result with an explanation. I tested it with three different purchases. The headphones cost $120, fit within a $300 budget, would be used about 12 times a month, and had already been considered for 14 days, so they received BUY. A desk lamp with lower use and only two days of consideration received WAIT. The limited-edition sneakers cost is nearly equal to the available budget, so they received SKIP. Seeing all three results appear correctly showed me that the main interaction was working. I also decided to show the percentage of the budget used and the estimated cost per use because a result without an explanation felt too random. If an item costs more than the user’s available spending money, the program gives it an automatic SKIP. I made that rule because I do not think frequent use should make an unaffordable purchase look reasonable.

Testing also showed me where the formula does not match the way I actually think about buying things. Some things are not used very often, but they can still bring a lot of happiness when they are used. The current formula mainly sees low usage as a negative, so it may undervalue this kind of purchase. AI cannot tell from the price and usage numbers how much an experience means to me. I thought about adding a happiness rating, but that did not feel very reliable either. If someone is excited about buying something, they may give it a high rating just to justify the purchase. For now, I left happiness out of the calculation and treated it as a limitation. AI helped me build the interface and create the first scoring system, but the weights were not objective. I still had to decide which rules made sense to me. The score boundaries also need more testing because they may not work the same way for everyone. Another problem is that the program uses six months to calculate cost per use for every purchase. That makes sense for some everyday products, but not for everything. Clothes may last for years, while a concert ticket is only used once and can still be worth the money. If I continue working on the project, I would change the calculation based on the type of purchase instead of judging everything with the same formula.
