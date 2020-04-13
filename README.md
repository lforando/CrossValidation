PS4: Implementing cross-validation
================

## What’s due when?

By Friday 2/28 at 9am you must do the following:

1.  Submit all your work (see next section) on GitHub. Any teams making
    submissions with timestamps after the above due date/time will be
    penalized 25% per day.
2.  Complete the [peer evaluation
    form](https://docs.google.com/forms/d/e/1FAIpQLSdA8lCnvglgDl5pWWN_epULa7LJSX3mDp0eA8_lLD1MFiQoIA/viewform).

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

## Team Info

Randomly assigned
teams:

| ps4        | name                    | github             | email                       |
| :--------- | :---------------------- | :----------------- | :-------------------------- |
| ps4-team01 | Elle Jo Whalen          | ewhalen1           | <ewhalen@smith.edu>         |
| ps4-team01 | Zoya Azhar              | zazharr            | <zazhar@smith.edu>          |
| ps4-team02 | Carol Liu               | CarolLiuSifan      | <cliu13@smith.edu>          |
| ps4-team02 | Serene Lee              | slee26             | <slee26@smith.edu>          |
| ps4-team03 | Lidia Ortiz             | lortiz34           | <lortiz34@smith.edu>        |
| ps4-team03 | Sarah Glidden           | saglidden          | <saglidden@smith.edu>       |
| ps4-team04 | Elisabeth Nesmith       | enesmith           | <enesmith@smith.edu>        |
| ps4-team04 | Roshni Patnayakuni      | Roshni-Patnayakuni | <rpatnayakuni@smith.edu>    |
| ps4-team05 | Alina Barylsky          | abarylsky          | <abarylsky@smith.edu>       |
| ps4-team05 | Riyao Yan               | riyaoy             | <ryan@smith.edu>            |
| ps4-team06 | Iris Wei                | iiiimsp            | <iwei@smith.edu>            |
| ps4-team06 | Lauren Forando          | lforando           | <lforando@smith.edu>        |
| ps4-team07 | Jeny Kwon               | jnkwon             | <jkwon@smith.edu>           |
| ps4-team07 | Jinghan Gao             | Jinghan18          | <jgao@smith.edu>            |
| ps4-team08 | Lizette Carpenter       | lcarpenter20       | <lcarpenter@smith.edu>      |
| ps4-team08 | Marisa Blackman         | mhblackman         | <mblackman@smith.edu>       |
| ps4-team09 | Emma Scott              | esscott            | <esscott@smith.edu>         |
| ps4-team09 | Irene Xu                | Irene-Xu-mengye    | <mxu50@smith.edu>           |
| ps4-team10 | Ruby Ru                 | RubyRu             | <rru@smith.edu>             |
| ps4-team10 | Sandy Shi               | SandyShi-yoyo      | <Sshi57@smith.edu>          |
| ps4-team11 | Lauren Meyer            | LyraDusk           | <lmeyer@smith.edu>          |
| ps4-team11 | Sophia Foster           | sophiamaya         | <smfoster@smith.edu>        |
| ps4-team12 | Lily Diao               | lilydiao           | <ldiao@smith.edu>           |
| ps4-team12 | Lily Jin                | Lilyyyy54          | <ljin54@smith.edu>          |
| ps4-team13 | Hannah Snell            | hmsnell            | <hsnell@smith.edu>          |
| ps4-team13 | Maggie Wang             | maggiexwang        | <xwang73@smith.edu>         |
| ps4-team14 | Anna Ballou             | aballou16          | <aballou@smith.edu>         |
| ps4-team14 | Karina Lieb             | karinalieb         | <klieb@smith.edu>           |
| ps4-team15 | Hana Hirano             | hnhirano           | <hhirano@smith.edu>         |
| ps4-team15 | Sunshine Schneider      | sunschneider       | <sschneider@smith.edu>      |
| ps4-team16 | Lucy Zhen               | Lucy-Z-7           | <zhen22x@mtholyoke.edu>     |
| ps4-team16 | Seren Smith             | Seren-Smith        | <Jlsmith@smith.edu>         |
| ps4-team17 | Laetitia Huang          | lhuang17           | <lhuang17@smith.edu>        |
| ps4-team17 | Sarah Weden             | sarahweden         | <sweden@smith.edu>          |
| ps4-team18 | Eunice Kim              | eukim89            | <ekim89@smith.edu>          |
| ps4-team18 | Valerie Medina Cebreros | Valerieeee         | <vmedinacebreros@smith.edu> |
| ps4-team19 | Finn Giardine           | fgiardine          | <fgiardine@smith.edu>       |
| ps4-team19 | Guy Incognito           | whoishomer         | <gincognito56@smith.edu>    |
