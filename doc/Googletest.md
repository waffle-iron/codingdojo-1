# Framework

# Introduction
## Before you start
```bash
git submodule update lib/googletest
```

## The docu
[A quick introduction to the Google C++ Testing Framework](http://www.ibm.com/developerworks/aix/library/au-googletestingframework.html)(

[Googletest - Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md)

[Googletest - Advancecd Guide](https://github.com/google/googletest/blob/master/googletest/docs/AdvancedGuide.md)

# Examples

[Googletest - Samples](https://github.com/google/googletest/blob/master/googletest/docs/Samples.md)

## Important Assertions
### Binary Assertions

| **Fatal assertion** | **Nonfatal assertion** | **Verifies** |
|:--------------------|:-----------------------|:-------------|
| `ASSERT_TRUE(`_condition_`)`;  | `EXPECT_TRUE(`_condition_`)`;   | _condition_ is true |
| `ASSERT_FALSE(`_condition_`)`; | `EXPECT_FALSE(`_condition_`)`;  | _condition_ is false |
( Taken from [Googletest - Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md))

### Math Assertions

| **Fatal assertion** | **Nonfatal assertion** | **Verifies** |
|:--------------------|:-----------------------|:-------------|
|`ASSERT_EQ(`_val1_`, `_val2_`);`|`EXPECT_EQ(`_val1_`, `_val2_`);`| _val1_ `==` _val2_ |
|`ASSERT_NE(`_val1_`, `_val2_`);`|`EXPECT_NE(`_val1_`, `_val2_`);`| _val1_ `!=` _val2_ |
|`ASSERT_LT(`_val1_`, `_val2_`);`|`EXPECT_LT(`_val1_`, `_val2_`);`| _val1_ `<` _val2_ |
|`ASSERT_LE(`_val1_`, `_val2_`);`|`EXPECT_LE(`_val1_`, `_val2_`);`| _val1_ `<=` _val2_ |
|`ASSERT_GT(`_val1_`, `_val2_`);`|`EXPECT_GT(`_val1_`, `_val2_`);`| _val1_ `>` _val2_ |
|`ASSERT_GE(`_val1_`, `_val2_`);`|`EXPECT_GE(`_val1_`, `_val2_`);`| _val1_ `>=` _val2_ |
( Taken from [Googletest - Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md))

### String Assertions
| **Fatal assertion** | **Nonfatal assertion** | **Verifies** |
|:--------------------|:-----------------------|:-------------|
| `ASSERT_STREQ(`_str1_`, `_str2_`);`    | `EXPECT_STREQ(`_str1_`, `_str_2`);`     | the two C strings have the same content |
| `ASSERT_STRNE(`_str1_`, `_str2_`);`    | `EXPECT_STRNE(`_str1_`, `_str2_`);`     | the two C strings have different content |
| `ASSERT_STRCASEEQ(`_str1_`, `_str2_`);`| `EXPECT_STRCASEEQ(`_str1_`, `_str2_`);` | the two C strings have the same content, ignoring case |
| `ASSERT_STRCASENE(`_str1_`, `_str2_`);`| `EXPECT_STRCASENE(`_str1_`, `_str2_`);` | the two C strings have different content, ignoring case |
( Taken from [Googletest - Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md))

### Floating Point Assertions
| **Fatal assertion** | **Nonfatal assertion** | **Verifies** |
|:--------------------|:-----------------------|:-------------|
| `ASSERT_FLOAT_EQ(`_expected, actual_`);`  | `EXPECT_FLOAT_EQ(`_expected, actual_`);` | the two `float` values are almost equal |
| `ASSERT_DOUBLE_EQ(`_expected, actual_`);` | `EXPECT_DOUBLE_EQ(`_expected, actual_`);` | the two `double` values are almost equal |
(Taken from [Googletest - Advancecd Guide](https://github.com/google/googletest/blob/master/googletest/docs/AdvancedGuide.md))

### Exception Assertions
| **Fatal assertion** | **Nonfatal assertion** | **Verifies** |
|:--------------------|:-----------------------|:-------------|
| `ASSERT_THROW(`_statement_, _exception\_type_`);`  | `EXPECT_THROW(`_statement_, _exception\_type_`);`  | _statement_ throws an exception of the given type  |
| `ASSERT_ANY_THROW(`_statement_`);`                | `EXPECT_ANY_THROW(`_statement_`);`                | _statement_ throws an exception of any type        |
| `ASSERT_NO_THROW(`_statement_`);`                 | `EXPECT_NO_THROW(`_statement_`);`                 | _statement_ doesn't throw any exception            |
(Taken from [Googletest - Advancecd Guide](https://github.com/google/googletest/blob/master/googletest/docs/AdvancedGuide.md))
