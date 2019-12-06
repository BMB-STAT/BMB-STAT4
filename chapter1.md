---
title: 'STAT4 - Hypothesis Testing'
description: 'Introducing hypothesis testing'
---

## The binomial test in R (2)

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
