# Improvements to Java analysis

The following changes in version 1.24 affect Java analysis in all applications.

## General improvements

* Alert suppression can now be done with single-line block comments (`/* ... */`) as well as line comments (`// ...`).

## New queries

| **Query**                   | **Tags**  | **Purpose**                                                        |
|-----------------------------|-----------|--------------------------------------------------------------------|

## Changes to existing queries

| **Query**                    | **Expected impact**    | **Change**                        |
|------------------------------|------------------------|-----------------------------------|
| Dereferenced variable may be null (`java/dereferenced-value-may-be-null`) | Fewer false positives | Final fields with a non-null initializer are no longer reported. |
| Expression always evaluates to the same value (`java/evaluation-to-constant`) | Fewer false positives | Expressions of the form `0 * x` are usually intended and no longer reported. |
| Useless null check (`java/useless-null-check`) | More true positives | Useless checks on final fields with a non-null initializer are now reported. |

## Changes to libraries
