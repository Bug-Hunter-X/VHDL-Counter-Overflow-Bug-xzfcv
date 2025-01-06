# VHDL Counter Overflow Bug

This repository demonstrates a common, yet subtle, bug in VHDL code: counter overflow.  The `buggy_counter.vhd` file contains a counter that uses an integer type, which can lead to unpredictable behavior when it exceeds its maximum value. The `fixed_counter.vhd` illustrates a corrected version.

## Problem

The original counter does not handle the case when the `internal_count` reaches its maximum value (15). When it increments past 15, it silently wraps around to 0. This might be unexpected and lead to incorrect functionality in a larger design.

## Solution

The solution uses a `std_logic_vector` to represent the counter.  This avoids the implicit wraparound of the `integer` type.  Appropriate handling is added to prevent further incrementing once the max value is reached.