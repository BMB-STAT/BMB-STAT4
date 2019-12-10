---
title: 'STAT4 - Hypothesis Testing'
description: 'Introducing hypothesis testing'
---

## Using qbinom 1

```yaml
type: NormalExercise
key: ca17dc7e86
lang: r
xp: 100
skills: 1
```

In the eModule you saw how to use the `qbinom()` function and now it's your turn. We can use this to calculate the critical value of a given distribution at a specific alpha. The first argument in qbinom is the proportion of the distribution you want to cover. In the video we first calculated the critical value for a one-tailed test, using 0.05 as our alpha. 

`@instructions`
Calculate the critical value in our fair coin example (59 heads out of 100 tries) when we use alpha = 0.05 and we plan to perform a one tailed test.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# calculating the critical value
qbinom()
```

`@solution`
```{r}
# calculating the critical value
qbinom(0.95, 100, 0.5)

```

`@sct`
```{r}
# test_function("qbinom", args = c("p", "size", "prob"))
ex() %>% check_function("qbinom") %>% {
  check_arg(., "p") %>% check_equal()
  check_arg(., "size") %>% check_equal()
  check_arg(., "prob") %>% check_equal()
}
```

---

## Using qbinom 2

```yaml
type: NormalExercise
key: 6440ecc0ef
lang: r
xp: 100
skills: 1
```

Next let's calculate the critical values of a two-tailed test in the same situation, using an alpha of 0.05.

`@instructions`
Calculate the two critical values in our fair coin example (59 heads out of 100 tries) when we use alpha = 0.05 and we plan to perform a two tailed test.

`@hint`
Now the 5% of alpha needs to be shared between the two ends of the distribution, so we need to perform two qbinom calculations.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# calculating the lower critical value

# calculating the upper critical value


```

`@solution`
```{r}
# calculating the lower critical value
qbinom(0.025, 100, 0.5)
# calculating the upper critical value
qbinom(0.975, 100, 0.5)
```

`@sct`
```{r}
# test_function("qbinom", args = c("p", "size", "prob"))
ex() %>% check_function("qbinom") %>% {
  check_arg(., "p") %>% check_equal()
  check_arg(., "size") %>% check_equal()
  check_arg(., "prob") %>% check_equal()
}
```

---

## Using qbinom 3

```yaml
type: NormalExercise
key: a9efbce237
lang: r
xp: 100
skills: 1
```

Let's use a different situation to practice using the qbinom function. 

We will return to our heart attack example from STAT3.

Remember, 4 out of every 100 people who suffer a heart attack die as a result of that attack.

15 people are admitted to hospital X with a heart attack and 3 of them die. 

A journalist is concerned that this is unusually high. He calculates 4% of 15, and gets the answer 0.6, but cannot interpret what this means for number of people (you can't get 0.6 of a person!).

You know that the critical value can give you a threshold of how many fatalities might be expected to occur, given the probability distribution.

The null hypothesis is that this hospital does not suffer more fatalities from heart attacks than expected.
The alternative hypothesis is that this hospital suffers more fatalities from heart attacks than expected.

`@instructions`
Calculate the critical value for a one-tailed analysis of this problem, using alpha as 0.05. The critical value would represent the number of people dying at this hospital as a result of heart attacks at which point we would become concerned that there is something unusual about the fatality rate at this hospital.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# calculating the critical value for heart attacks at hospital X

```

`@solution`
```{r}
# calculating the critical value for heart attacks at hospital X
qbinom(0.95, 15, 0.04)

```

`@sct`
```{r}
# test_function("qbinom", args = c("p", "size", "prob"))
ex() %>% check_function("qbinom") %>% {
  check_arg(., "p") %>% check_equal()
  check_arg(., "size") %>% check_equal()
  check_arg(., "prob") %>% check_equal()
}
```

---

## Using qbinom 4

```yaml
type: NormalExercise
key: fbce8101d9
lang: r
xp: 100
skills: 1
```

Next let's calculate the critical values of a two-tailed test in the same situation, using an alpha of 0.05.

Remember, 4 out of every 100 people who suffer a heart attack die as a result of that attack.

15 people are admitted to hospital X with a heart attack and 3 of them die. 

The null hypothesis is that this hospital does not suffer any _more or less_ fatalities from heart attacks than expected.
The alternative hypothesis is that this hospital suffers more fatalities from heart attacks than expected.

`@instructions`
Calculate the two critical values in the heart attack example when we use alpha = 0.05 and we plan to perform a two tailed test.

`@hint`
Now the 5% of alpha needs to be shared between the two ends of the distribution, so we need to perform two qbinom calculations.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# calculating the lower critical value

# calculating the upper critical value


```

`@solution`
```{r}
# calculating the lower critical value
qbinom(0.025, 15, 0.04)
# calculating the upper critical value
qbinom(0.975, 15, 0.04)
```

`@sct`
```{r}
# test_function("qbinom", args = c("p", "size", "prob"))
ex() %>% check_function("qbinom") %>% {
  check_arg(., "p") %>% check_equal()
  check_arg(., "size") %>% check_equal()
  check_arg(., "prob") %>% check_equal()
}
```

---

## Is there cause for concern?

```yaml
type: MultipleChoiceExercise
key: 5be25c22fa
xp: 50
```

<!-- Guidelines for the question: https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises. -->
Given the critical values you have calculated, do you think there is cause for the journalist to be concerned that 3 out of 15 people have suffered fatal heart attacks?

`@possible_answers`
- [this is an unusual outcome in both the one-tailed and two-tailed analysis]
- this is an unusual outcome but only in the one-tailed analysis
- this outcome is impossible given the null hypothesis
- we can accept the alternative hypothesis

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- If you need to remind yourself of the critical values, use the qbinom() in the console, or look back at the previous questions.

`@pre_exercise_code`
```{r}

```

`@sct`
```{r}
# Check https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises on how to write feedback messages for this exercise.
msg1 <- "Correct! The number of fatalities is greater than the critical value, but at this point we cannot say anything more than it is an unusual outcome. We could also argue that in this case, a one-tailed analysis is appropriate, as we are dealing with issues of fatality, and we are not very interested in whether the hospital has a lower than expected fatality rate."
msg2 <- "This is an incorrect interpretation of the critical values calculated - you get the same critical value for both one- and two-tailed analyses"
msg3<-"This is incorrect - we do not yet have enough evidence to suggest that this outcome is impossible, or even highly unlikely at this point, just that it is unusual"
msg4 <- "Despite the fact we can reject the null hypothesis, we would never then complete this statement with an acceptance of the alternative hypothesis - as it stands, there is still a 5% chance that this result or more extreme could be observed if the null hypothesis was true"

ex() %>% check_mc(1, feedback_msgs = c(msg1, msg2, msg3, msg4))
```

---

## Using qbinom 5

```yaml
type: NormalExercise
key: d7e636653e
lang: r
xp: 100
skills: 1
```

The journalist wants to be sure that this outcome is highly unlikely, and asks you to change the alpha.

You decide to use an alpha of 0.001 and a one-tailed test, to indicate that you would only expect this outcome or more extreme less than 0.1% of the time if the null hypothesis was true, and you decide that this is highly unlikely. 

The null hypothesis is that this hospital does not suffer more fatalities from heart attacks than expected.
The alternative hypothesis is that this hospital suffers more fatalities from heart attacks than expected.


`@instructions`
Calculate the critical value using an alpha of 0.001.

`@hint`
Remember this is a one-tailed analysis so you only need to calculate 1 critical value.

`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}



```

`@solution`
```{r}
qbinom(0.999,15,0.04)

```

`@sct`
```{r}
# test_function("qbinom", args = c("p", "size", "prob"))
ex() %>% check_function("qbinom") %>% {
  check_arg(., "p") %>% check_equal()
  check_arg(., "size") %>% check_equal()
  check_arg(., "prob") %>% check_equal()
}
```

---

## Interpreting the result

```yaml
type: MultipleChoiceExercise
key: caaf32b850
xp: 50
```

<!-- Guidelines for the question: https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises. -->
Given the critical values you have calculated, do you think there is cause for the journalist to be concerned that 3 out of 15 people have suffered fatal heart attacks at hospital X?

`@possible_answers`
- the number of fatalities is greater than the critical value for alpha = 0.05, therefore this is a statistically significant result.
- we can accept the alternative hypothesis in this situation
- [This outcome is unlikely, but it is difficult to say that it is very highly unlikely.]
- we should have used a two-tailed test to be sure

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- The critical value using an alpha of 0.05 is 2
- The critical value using an alpha of 0.001 is 4

`@pre_exercise_code`
```{r}

```

`@sct`
```{r}
# Check https://instructor-support.datacamp.com/en/articles/2375523-course-multiple-choice-with-console-exercises on how to write feedback messages for this exercise.
msg3 <- "Correct! The number of fatalities is greater than the critical value for alpha=0.05, but less than the critical value for alpha=0.001. Therefore it is unlikely to occur 5% of the time, but not unexpected 0.1% of the time. We could also argue that in this case, a one-tailed analysis is appropriate, as we are dealing with issues of fatality, and we are not very interested in whether the hospital has a lower than expected fatality rate."
msg4 <- "We could also argue that in this case, a one-tailed analysis is appropriate, as we are dealing with issues of fatality, and we are not very interested in whether the hospital has a lower than expected fatality rate."
msg1<-"This is incorrect - at an alpha of 0.05 we are not able to suggest that this outcome is impossible, or even highly unlikely at this point, just that it is unusual. Merely specifying that this is statistically significant is not a useful interpretation."
msg2 <- "Despite the fact we can reject the null hypothesis, we would never then complete this statement with an acceptance of the alternative hypothesis - as it stands, there is still a 0.1% chance that this result or more extreme could be observed if the null hypothesis was true"

ex() %>% check_mc(3, feedback_msgs = c(msg1, msg2, msg3, msg4))
```

---

## The binomial test in R

```yaml
type: NormalExercise
key: 5d094e21fe
lang: r
xp: 100
skills: 1
```

In the eModule you saw how to use the `binom.test()` function and now it's your turn.

`@instructions`
Perform a binomial test on the probability of getting 59 heads from 100 throws of a hypothetically fair coin.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Binomial test on 59 heads from 100 throws

```

`@solution`
```{r}
# Binomial test on 59 heads from 100 throws
binom.test(59, 100, 0.5)

```

`@sct`
```{r}
# test_function("binom.test", args = c("x", "n", "p"))
ex() %>% check_function("binom.test") %>% {
  check_arg(., "x") %>% check_equal()
  check_arg(., "n") %>% check_equal()
  check_arg(., "p") %>% check_equal()
}
```

---

## The binomial test in R 2

```yaml
type: NormalExercise
key: cdf251ae37
lang: r
xp: 100
skills: 1
```

Now lets try with our heart attack example

`@instructions`
Perform a binomial test on the probability of 3 fatalities out of 15 heart attacks occurring at hospital X, given a fatality likelihood of 0.04.

`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}
# Binomial test on 3 fatalities out of 15 heart attacks

```

`@solution`
```{r}
# Binomial test on 3 fatalities out of 15 heart attacks
binom.test(3, 15, 0.04)

```

`@sct`
```{r}
# test_function("binom.test", args = c("x", "n", "p"))
ex() %>% check_function("binom.test") %>% {
  check_arg(., "x") %>% check_equal()
  check_arg(., "n") %>% check_equal()
  check_arg(., "p") %>% check_equal()
}
```
