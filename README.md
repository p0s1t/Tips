# Tips
Java based algorithm that uncovers trading patterns through linear regression and Bayesian logic

I wrote this as a sort of tribute to my ten years spent as a waiter while I was working my way through college. Hoping it provides
some 'tips' that one can use to derive some profit from consistent trading patterns.

The general idea is that there are recognizable trading patterns that can be derived through creating trading rules that are based on 
technical indicators that are commonly used by day-traders and fund managers. 

So far, the sgorithm has been pretty successful, and while I haven't had much capital to invest, my simulations have demonstrated
an average annual return of about 20%. I only used the Dow 30 (those equities that comprise the Dow/Jones Index) because being
as large cap as they are they tend to follow established patterns due to massive trading volume and resistance to serious volatility.

I introduced some elements of AI into this algorithm because I love AI and I figured it'd be a fun way to try out some of the 
tools I learned in school. Those elements are:

1) cross validation - I wrote trading rules that would work in smaller blocks of each respective stock's trading history, and then
projected those rules onto a testing set after creating a fitness function to determine the 'best' (generally meaning the most robust)
rules. I used a certain amount of stochastocity in the size of the cross validation subsets to avoid any patterns that might work
within a very small range or only when certain trading behavior was present and not over the full range of the trading history. This
strategy proved very effective.

2) mutation operators - generally found in genetic algorithms, I used a mutation operator for a few of the metrics involed within the 
scope of technical indicators. So, for example, the period of a relative strength indix indicator might be 14, but I would mutate (vary)
that operator randomly to within +/- 5 periods or +/- 40% of the generally accepted range to see what results I could tease out of the data.

3) Bayesian logic - so, because there are both buying a selling rules I knew I was going to be up against a <i>large</i> amount of possibilities
and I figured the best way to sort through them all was to use a Bayesian tree structure with a fairly conservative branching factor, which
I also mutated, to ensure that I was avoiding the trap of overfitting the data. The best rules ended up having a branching factor typically
between 3 and 6, i.e. each buying and selling rule would take into account between 3 and 6 different indicators when trading. I used Boolean
logic operators in between each rule element to get the most fit trading rule, so that there are AND/OR/NOR/XOR to cover all possible rule behaviors.

And that's basically it. I am presently designing a front end to this, and but am reserving that code until I have something resonably presentable to upload.

Hopefully, I'll have some discretionary income in the near term so I can put my money where my mouth is and really see if this generates some passive income.

