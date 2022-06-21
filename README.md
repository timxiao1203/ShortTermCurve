# Short Term Curve

Short term curve construction may contain both regular and serial futures contracts that results in a significant amount of underlying term overlapping. The overlapping may lead to widely oscillating Partial Differential Hedge (PDH) numbers.

A method, called Time Weighted Quadratic Average, is proposed. The model solves the problem of overlapping short-end input instrument (deposits and futures) terms When faced with an input instrument set containing both regular and serial 3-month futures contracts, the model partitions the full set into 3 subsets, that is, creates three mutually disjoint subsets whose union is the original set: 

First subset is made of the futures whose delivery month numbers (June is 6, i.e. the sixth month in the year) give remainder 0 when divided to 3 (so-called the mod 0 group), 

Second subset is made of the futures whose delivery month numbers give remainder 1 when divided to 3 (so-called the mod 1 group), 

Third subset is made of the futures whose delivery month numbers give remainder 2 when divided to 3 (so-called the mod 2 group).

Start and end dates of the underlying terms of futures contracts become the so-called offset days. The sets of offset dates corresponding to different mod groups do not intersect.

If we have the discount factor at the first offset date of a mod group, then, using the forward wealth factor multiplicative property and normalization process, one can construct the discount factors at the rest of offset dates in the group. The cash deposits produce discount factors at their underlying term start and end dates, call them cash dates. The discount factor at the first offset date of a mod group, so-called seed, will be deduced via interpolation from the discount factors at the nearest (left and right) cash dates.

Once we independently apply the above procedure for each of the three mod groups, we end up with three series of discount factors at three disjoint series of offset dates. We also have the discount factors at the cash dates. We form the final set of curve anchor dates from all offset dates and all cash dates. So, we obtain discount factors at all anchor dates. At any intermediate date we produce a discount factor by interpolating between the discount factors at the nearest (left and right) neighboring anchor dates.

From market futures contract yields, using the correct conventions, we can easily determine forward rates for the corresponding term, and, accordingly, the forward discount factors (wealth factors).


Reference:

https://finpricing.com/lib/EqConvertible.html

https://zenodo.org/record/6671596#.YrCdCnYpBD8

https://zenodo.org/record/6671596/files/shortTermCurve.pdf
