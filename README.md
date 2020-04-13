Implementing cross-validation
================

## Your work

You will be implementing an algorithm to obtain the “optimal” complexity
parameter value `cp` of a CART model using estimates of Kaggle scores
computed via cross-validation . You’ll be doing this “from scratch”
using `dplyr` and other basic R functions. While cross-validation is
implemented in any machine learning software package, it’s important to
code it up once to really understand what’s going on. Much like when you
learn long division or matrix multiplication, you do it by hand a few
times at first, but then afterwards you only use a calculator/computer.

1.  You be fitting CART models of the form:  
    `rpart(SalePrice ~ GrLivArea + HalfBath + YearBuilt)`
2.  For an arbitrarily chosen `cp` value, implement k = 5 fold
    cross-validation where:
    1)  the value of `k` is programmed *dynamically* and not
        *hard-coded*
    2)  It produces an estimate of the Kaggle RMSLE. Hint: There is a
        way to verify that your estimated RMSLE isn’t “drastically
        wrong.” While you don’t need to show this work, you should do
        this sanity check on your own.
3.  Using your implementation of k = 5 fold cross-validation, identify
    the “optimal” `cp` value to use in a Kaggle submission:
    1)  Define a *search grid* of 101 `cp` values. Hint: You may need to
        iteratively refine your search grid of `cp` values to ensure
        that you’ve found the “optimal” one.
    2)  For each of these 101 values of `cp`, the estimated RMSLE
    3)  Plot a scatterplot with `cp` on the x-axis and estimated RMLSE
        on the y-axis.
    4)  Visually pick which `cp` value you think is “optimal.” Call this
        `cp_star`
4.  Make a submission to Kaggle using `cp_star` and compare your
    estimated RMSLE with that one returned by Kaggle

## Suggested workflow

1.  Be sure to consult the MassMutual RStudio Project `coding.Rmd` file
    often. Almost all the code you’re going to need can be found there.
2.  Knit `PS4.Rmd` and read all instructions.
3.  You will need to use two nested `for` loops for this problem set.
    Keeping with the spirit of “minimally viable products,” I suggest
    you ensure your inner `for` loop works correctly first, commit/push
    to GitHub, then ensure your outer `for` loop works, commit/push to
    GitHub, then complete the rest of the problem set.

## Evaluation criteria

From most to least important:

1.  **“If others can’t reproduce your work, they will throw it in the
    trash.”** Submissions that don’t knit will be penalized harshly.
2.  **“Presentation and communication-style matters.”** Related to point
    above, for example
      - Plots: Keep the “ink-to-information” ratio in mind. Ensure your
        plots have labeled axes and informative titles.
      - Use markdown formatting to make your presentation effective.
      - Is code cleanly written, well-documented, and well-formatted. As
        the semester progresses, I’ll be giving feedback from [The
        tidyverse style guide](https://style.tidyverse.org/)
3.  **“Did you work as a team?”**
      - Since you will be pair programming, Git commits won’t be looked
        at as closely
      - Peer evaluations (goes to your engagement grade).
4.  **Algorithm** (in this order of importance):
      - Does cross-validation algorithm return valid RMSLE estimates.
      - Do you apply your cross-validation algorithm to 101 values of
        `cp` to compute 101 RMSLE estimates?
      - Does your visualization show that you’ve identified the
        “optimal” `cp` value?
      - Does your fitted CART model using the “optimal” `cp` return a
        valid Kaggle score?
