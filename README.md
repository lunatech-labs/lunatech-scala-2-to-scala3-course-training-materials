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

- Unzip the `LSL-E-lightbend-scala-language-expert.zip` archive in a location of your choice.

- Set the current course the the *Scala Language Expert* course by running the
  `cmtc set-root` command. For example, assuming you unzipped the course in a folder
  `Courses` in your home directory, you should run the following command:

```bash
$ cmtc set-current-course -s ~/Courses/LSL-E-lightbend-scala-language-expert
Current course set to '~/Courses/LSL-E-lightbend-scala-language-expert'
```

We can verify this operation by running the `cmtc list-exercises` command to display
the exercises in the course:

```bash
$ cmtc list-exercises
  1.  *   exercise_000_initial_state
  2.      exercise_001_tail_recursive_operation
  3.      exercise_002_use_forall_and_sliding
  4.      exercise_003_folding
  5.      exercise_004_calculate_connections_I
  6.      exercise_005_calculate_connections_II
  7.      exercise_006_calculate_connections_III
  8.      exercise_007_calculate_connections_IV
  9.      exercise_008_calculate_connections_V
 10.      exercise_009_custom_value_classes
 11.      exercise_010_create_a_queue_I
 12.      exercise_011_create_a_queue_II
 13.      exercise_012_create_a_queue_III
 14.      exercise_013_covariance
 15.      exercise_014_upper_bounds
 16.      exercise_015_lower_bounds
 17.      exercise_016_feeding_animals_outline
 18.      exercise_017_feeding_animals
 19.      exercise_018_implicit_conversions_I
 20.      exercise_019_implicit_conversions_II
 21.      exercise_020_extend_my_library
 22.      exercise_021_type_classes
 23.      exercise_022_context_bounds
 24.      exercise_023_implicit_parameter_chaining
 25.      exercise_024_group_exercise_custom_control_abstractions
 26.      exercise_025_custom_control_abstractions
 27.      exercise_026_DSL_for_time
 28.      exercise_027_DSL_for_train
 29.      exercise_028_calculate_connections_async
```

## Verifying `sbt` and the course

A quick verification of your Java and sbt setup can be performed as follows:

```bash
$ cd ~/Courses/LSL-E-lightbend-scala-language-expert

$ cd code

$ sbt
[info] Loading settings for project global-plugins from idea.sbt ...
...
<elided>
...

sbt:LSL-E-lightbend-scala-language-expert> test
[info] compiling 3 Scala sources to /Users/ericloots/tmp/stu/LSL-E-lightbend-scala-language-expert/code/target/scala-2.13/classes ...
[info] compiling 4 Scala sources to /Users/ericloots/tmp/stu/LSL-E-lightbend-scala-language-expert/code/target/scala-2.13/test-classes ...
[info] TimeSpec:
[info] Creating a Time
[info] - should throw an IllegalArgumentException for hours not within 0 and 23
[info] - should throw an IllegalArgumentException for minutes not within 0 and 59
[info] The default arguments for hours and minutes
[info] - should be equal to 0
[info] asMinutes
[info] - should be initialized correctly
[info] Calling minus or -
[info] - should return the correct difference in minutes
[info] Calling toString
[info] - should return a properly formatted string representation
[info] Calling Ordered operators
[info] - should work as expected
[info] TrainSpec:
[info] Train 'green'
[info] - should stop in Nuremberg
[info] - should not stop in Essen
[info] Train 'red'
[info] - should stop in Munich
[info] - should not stop in Stuttgart
[info] Creating a Train
[info] - should throw an IllegalArgumentException for a schedule with 0 or 1 elements
[info] stations
[info] - should be initialized correctly
[info] JourneyPlannerSpec:
[info] stations
[info] - should be initialized correctly
[info] Calling trainsAt
[info] - should return the correct trains
[info] Calling stopsAt
[info] - should return the correct stops
[info] Calling isShortTrip
[info] - should return false for more than one station in between
[info] - should return true for zero or one stations in between
[info] Run completed in 412 milliseconds.
[info] Total number of tests run: 18
[info] Suites: completed 3, aborted 0
[info] Tests: succeeded 18, failed 0, canceled 0, ignored 0, pending 0
[info] All tests passed.
[success] Total time: 6 s, completed 16 Feb 2023, 16:36:53
sbt:LSL-E-lightbend-scala-language-expert>
```

*You're all set!*

