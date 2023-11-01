# Akash-T-ASE.github.io
# Akash-T-ASE.github.io


# Test out the site go niners
# Josh McDaniels from the Raiders should of been released

Internet Edge Routing with Arista FlexRoute
By: Alan Sukiennik, SE SouthWest Region

Several techniques are traditionally used for the ASIC routing table lookups:

TCAM – where the entire table is searched on every access, however half of that table is wasted on mask bits – interestingly, this approach uses the highest power, highest resource utilization, and produces the least results
Tree method – where multiple lookups are allowed, but the implementation of the tree lookups are often not efficient. However, it is algorithmic and better than the TCAM approach, but still not great.
And in Arista's case, it's FlexRoute – a very efficient, fully algorithmic technique where we use the least amount of active silicon resources. It's efficient in terms of storage on the chip, and the results are much better for the lookups than any alternative approaches.


So, what is FlexRoute? Essentially we, at Arista, had figured out a way to use the merchant silicon in a way that many others have not. For the other vendors in the industry to provide similar performance to Arista, they use custom chips. For all its capabilities, custom, proprietary silicon tends to be very expensive because companies spend a lot of time and money on developing and manufacturing those chips. Also, for those reasons, custom silicon tends to have very long life cycles, which, given the rapid advancements in network technologies, may not often be desirable. Arista, on the other hand, traditionally uses merchant silicon. Still, we apply the software R&D to do some incredible things with those chips and achieve performance as capable as that of custom silicon but at a significantly lower price point because the ASIC maker, such as Broadcom, has already done all the chip development work for us. Essentially it’s Arista software implementation that differentiates things. And one of these software innovations is called FlexRoute.



FlexRoute is hardware and software – one doesn't work without the other. It has to do with how EOS is architected and how we program the tables. It represents how we do more efficient L3 programming in hardware. It showcases how we could take that merchant silicon, the same merchant silicon that everyone else is using, and extract more out of those chips than even the silicon vendors decided they could. For example, let's go by Broadcom's numbers. They show LPM (Longest-Prefix-Match - the memory space where IP FIB is stored) going up to 256K prefixes on a Jericho, and approximately half a million on J2, while we're using the same silicon to extract more than four times that number. Jericho has a programmable packet parser and flexible lookups. Still, we taught it some new tricks of how you can do packet parsing much more efficiently and do the lookups into those tables in a way that allows us to extract very large table scopes. We do not use Broadcom SDK for programming tables. The standard way they do that does not support getting these very large table sizes out of the chip itself, so this is pure Arista innovation at play here.

The letter R in the Arista switching platform name stands for the ability to use FlexRoute. For example, 7280R3 is where R STANDS for FlexRoute, and if there is K in the name, as in 7280R3K, then it stands for KAPS, Broadcom's name for the LPM table. The K models further increase the capacity of the tables. Additionally, non-Internet Edge use cases for KAPS offer a considerable increase in ACL capacity.

So, what is the routing scale that we can achieve with FlexRoute? Using the default Internet profile on Arista 7280R3, we can get up to 2,500.000 prefixes, with some additional optimizations that can scale up even further. Given that today's full Internet BGP table size is roughly 930,000 prefixes, the routing capacity that an Arista switch can provide covers pretty much any use case today, tomorrow, and the day after.
Click here to learn more about Arista Flexroute.

