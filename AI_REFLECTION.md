

 1. Audit table (CHECK phase)

I pasted the statistics table from `2_work.ipynb` into an AI interpretation session and colour-coded every sentence of the AI’s reply.

| Claim in AI reply | Colour | Action taken | Reason |
|-------------------|--------|--------------|--------|
| “All four items show clear upward trends” | green | Accepted | Recomputable from first-to-last % changes |
| “Sweetener D rose almost 20 %” | green | Accepted | 19.41 % matches notebook |
| “The mean is more reliable than the median for these data” | amber | Rejected | Explanation only; no supporting calculation offered |
| “City 2 is systematically more expensive because of higher transport costs” | red | Rejected | Causal claim not supported by the data; we have no cost information |
| “Pulse C is essentially flat” | amber | Softened | 3.69 % is small but positive; “essentially flat” is interpretive |
| Exact numbers for mean/median of each item | green | Accepted after recompute | Matched notebook to two decimal places |
| “One outlier in Oil B would reverse the conclusion” | red | Rejected | Sensitivity check shows median unchanged and mean still higher |

Rule I followed: green = I can recompute it from the notebook; amber = plausible explanation but not proven; red = causal leap or reference to data I never supplied.

 
“But why isn’t the mean the typical price? Everyone uses the mean. If the mean went up, the price went up, right? Why do we even need the median?”

My explanation (kept asking until the questions stopped): The mean is just the total of all the prices divided by how many there are. One unusually high or low reading pulls it. The median is the middle value once you line the prices up in order; half the observations are below it and half above. In this particular file the two numbers sit almost on top of each other, so either one tells the same story about the level. The question the neighbours are really fighting about, though, is the *change*. For that the cleanest single figure is the percentage difference between the first week’s average and the last week’s average. That number does not care whether you prefer the mean or the median of the whole sample.

(The AI stopped repeating the same objection after two rounds of this distinction between level and change.)

3. Reflection (REFLECT phase)

The first draft in `1_attempt.md` already contained the core numbers and the central claim that both mean and median point the same way. What the later steps added was precision of language and a clearer separation of observation, explanation and causal claim.  

The most useful correction was realising that “the price went up” is best answered by an endpoint comparison, not by a comparison of two different averages of the whole sample. Once that was clear, the mean-versus-median quarrel became secondary: both averages describe the level, while the first-to-last percentage change describes the movement the neighbours actually care about.

I also learned that a single flagged value can move the mean by a couple of rupees while leaving the median untouched; that is why the sensitivity check belongs in the note.

