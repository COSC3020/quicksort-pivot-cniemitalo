# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

### My answer 

Picking the pivot as the first element in a randomly sorted array means that every element has an equal chance of being selected, so based on slide 34, there is a 50% chance of picking a pivot within the middle half of the array (a good pivot), and a 50% chance of picking a pivot either less than or greater than that middle half (a bad pivot). Of that 50% chance of picking a bad pivot, there is a 25% chance of picking a pivot less than and a 25% chance of picking a pivot greater than. 

There are 10 possible combinations if three elements are picked out of a randomized array. The options are less than good pivot values (L), greater than good pivot values (G), and middle, good pivot, values (M). The 6 combinations MMM (x1), LLM (x3), GGM (x3), MMG (x3), MML (x3), and LMG (x6), each of them is multiplied by the number of different ways they can be arranged, are the only ones where a middle (good pivot) is selected at all.

The probabilities of these combinations occuring are: 

MMM = $(1/2) * (1/2) * (1/2) = 1/8$

LLM = $(1/4) * (1/4) * (1/2) = 1/32$ 

GGM = $(1/4) * (1/4) * (1/2) = 1/32$ 

MMG = $(1/2) * (1/2) * (1/4) = 1/16$

MML = $(1/2) * (1/2) * (1/4) = 1/16$

LMG = $(1/4) * (1/2) * (1/4) = 1/32$

As the median of three chooses the median element to use, we have to remove the combinations LLM and GGM, as both of them would not select the good pivot value as the pivot. (L <= L <= M, so a lower element would be chosen, and M <= G <= G, so a greater element would be chosen). The total possibility would then be $(1/8) + 3(1/16) + 3(1/16) + 6(1/32) = 0.6875$ giving us a 68.75% chance of choosing a good pivot using the median of three method.

The median of three method is therefore more likely to select a good pivot than simply selecting the first element as 68.75% is greater than 50%. 

## Sources and Plagiarism 

I referenced Ishita Patel's repo to get an understanding of how to start this exercise. 

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.



