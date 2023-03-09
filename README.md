# Lunatech Moving from Scala 2 to Scala 3 course

## Course exercise set-up prerequisites

A laptop with the following installed:

- JDK 11
- sbt (see [here](https://www.scala-sbt.org/1.x/docs/Setup.html) for instructions) 

## Course set-up instructions

- Install the `cmtc` executable on your laptop and make sure it's executable and
  on your execution **PATH**.

> NOTE: Windows users should install both the `cmtc` **AND** the `cmtc.bat` files
  in the **same** folder on their system.

- Verify that `cmtc` can be executed by running it. The command should produce the
  output as shown here:

```bash
$ cd

$ cmtc
Usage: cmtc <COMMAND>

Commands:
  goto-exercise        Move to a given exercise. Pull in tests and readme files for that exercise
  goto-first-exercise  Move to the first exercise. Pull in tests and readme files for that exercise
  list-exercises       List all exercises and their IDs in the repo. Mark the active exercise with a star
  list-saved-states    List all saved exercise states, if any.
  next-exercise        Move to the next exercise. Pull in tests and readme files for that exercise
  previous-exercise    Move to the previous exercise. Pull in tests and readme files for that exercise
  pull-solution        Pull in all code for the active exercise. All local changes are discarded
  pull-template        Selectively pull in a given file or folder for the active exercise
  restore-state        Restore a previously saved exercise state
  save-state           Save the state of the active exercise
  set-current-course   Sets the current course to point to a directory
```

- Unzip the `lunatech-scala-2-to-scala3-course.zip` archive in a location of your choice.

- Set the current course the the *Lunatech - Moving from Scala 2 to Scala 3* course by running the
  `cmtc set-root` command. `cd` into the unzipped folder and run the `cmtc set-root` command
  as follows:

```bash
$ cd lunatech-scala-2-to-scala3-course

$ cmtc set-current-course -s .
Current course set to '/Users/ericloots/tmp/stu/lunatech-scala-2-to-scala3-course/.'

Exercises in repository:
  1.  *   exercise_000_sudoku_solver_initial_state
  2.      exercise_001_dotty_deprecated_syntax_rewriting
  3.      exercise_002_dotty_new_syntax_and_indentation_based_syntax
  4.      exercise_003_top_level_definitions
  5.      exercise_004_parameter_untupling
  6.      exercise_005_extension_methods
  7.      exercise_006_using_and_summon
  8.      exercise_007_givens
  9.      exercise_008_enum_and_export
 10.      exercise_009_union_types
 11.      exercise_010_opaque_type_aliases
 12.      exercise_011_multiversal_equality
 13.      exercise_020_opaque_type_aliases_alt
 14.      exercise_021_multiversal_equality
```

We can verify this operation by running the `cmtc list-exercises` command to display
the exercises in the course:

```bash
$ cmtc list-exercises
  1.  *   exercise_000_sudoku_solver_initial_state
  2.      exercise_001_dotty_deprecated_syntax_rewriting
  3.      exercise_002_dotty_new_syntax_and_indentation_based_syntax
  4.      exercise_003_top_level_definitions
  5.      exercise_004_parameter_untupling
  6.      exercise_005_extension_methods
  7.      exercise_006_using_and_summon
  8.      exercise_007_givens
  9.      exercise_008_enum_and_export
 10.      exercise_009_union_types
 11.      exercise_010_opaque_type_aliases
 12.      exercise_011_multiversal_equality
 13.      exercise_020_opaque_type_aliases_alt
 14.      exercise_021_multiversal_equality
```

## Verifying `sbt` and the course

A quick verification of your Java and sbt setup can be performed as follows
(assuming you're in the unzipped exercises folder):



```bash
$ cd code

$ sbt
[info] Loading settings for project global-plugins from idea.sbt ...
...
<elided>
...

$ sbt test
[info] welcome to sbt 1.8.2 (Eclipse Adoptium Java 11.0.18)
[info] compiling 11 Scala sources to /Users/ericloots/tmp/stu/lunatech-scala-2-to-scala3-course/code/target/scala-2.13/classes ...
[info] compiling 4 Scala sources to /Users/ericloots/tmp/stu/lunatech-scala-2-to-scala3-course/code/target/scala-2.13/test-classes ...
org.lunatechlabs.dotty.sudoku.CellMappingSuite:
org.lunatechlabs.dotty.sudoku.ReductionRuleSuite:
  + Mapping row coordinates should result in correct column & block coordinates 0.021s
  + Mapping column coordinates should result in correct row & block coordinates 0.001s
  + Mapping block coordinates should result in correct row & column coordinates 0.001s
  + Applying reduction rules should eliminate values in isolated complete sets from occurrences in other cells (First reduction rule) 0.047s
  + Applying reduction rules should eliminate values in isolated complete sets of 5 values from occurrences in other cells (First reduction rule) 0.001s
  + Applying reduction rules should eliminate values in 2 isolated complete sets of 3 values from occurrences in other cells (First reduction rule) 0.001s
  + Applying reduction rules should eliminate values in shadowed complete sets from occurrences in same cells (Second reduction rule) 0.002s
  + Applying reduction rules should eliminate values in shadowed complete (6 value) sets from occurrences in same cells (Second reduction rule) 0.0s
SLF4J: A number (1) of logging calls during the initialization phase have been intercepted and are
SLF4J: now being replayed. These are subject to the filtering rules of the underlying logging system.
SLF4J: See also http://www.slf4j.org/codes.html#replay
org.lunatechlabs.dotty.sudoku.SudokuDetailProcessorSuite:
  + Sending no updates to a sudoku detail processor should result in sending a SudokuDetailUnchanged messsage 0.007s
  + Sending an update to a fresh instance of the SudokuDetailProcessor that sets one cell to a single value should result in sending an update that reflects this update 0.002s
  + Sending a series of subsequent Updates to a SudokuDetailProcessor should result in sending updates and ultimately return no changes 0.003s
[info] Passed: Total 11, Failed 0, Errors 0, Passed 11
[success] Total time: 5 s, completed 9 Mar 2023, 17:21:24
```

*You're all set!*

