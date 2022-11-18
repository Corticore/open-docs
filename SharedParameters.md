# Level Design Shared Parameters Documentation

## Table of Content

- [Settings Table](#Settings)
  - [ScanMode](#ScanMode)
  - [BallSize](#BallSize)
  - [DifficultyRank](#DifficultyRank)
  - [LeftStartPassObjective](#LeftStartPassObjective)
  - [RightStartPassObjective](#RightStartPassObjective)
  - [MaxLeftPositionPassObjective](#MaxLeftPositionPassObjective)
  - [MaxRightPositionPassObjective](#MaxRightPositionPassObjective)
  - [MaxUpperPositionPassObjective](#MaxUpperPositionPassObjective)
  - [MinLowerPositionPassObjective](#MinLowerPositionPassObjective)
  - [MaxNearPositionPassObjective](#MaxNearPositionPassObjective)
  - [MaxFarPositionPassObjective](#MaxFarPositionPassObjective)
  - [WeatherEffect](#WeatherEffect)
  - [WeatherIntensity](#WeatherIntensity)
  - [EnableSupporters](#EnableSupporters)
  - [TeamSupportersRatio](#TeamSupportersRatio)
  - [OpponentSupportersRatio](#OpponentSupportersRatio)
- [Passes Table](#Passes)
  - [BallSize](#Id)
  - [BallSpeed](#BallSpeed)
  - [PassGiverTarget](#PassGiverTarget)
  - [IsRandomPassGiverTarget](#IsRandomPassGiverTarget)
  - [PassGiverTargetMinDistance](#PassGiverTargetMinDistance)
  - [PassGiverTargetMaxDistance](#PassGiverTargetMaxDistance)
  - [HasRandomLoops](#HasRandomLoops)
  - [HapticConstraintProbability](#HapticConstraintProbability)
- [PassLoops Table](#PassLoops)
  - [AssignedToPassId](#AssignedToPassId)
  - [IsHandConstrained](#IsHandConstrained)
  - [IsHapticConstrained](#IsHapticConstrained)
  - [ExpectedHandSide](#ExpectedHandSide)
  - [RelevantForEvaluation](#RelevantForEvaluation)

# Shared Parameters

## Settings

Table contains parameters that belong to the whole Level.

### ScanMode

Determines how to interprete the loops. Switches between our play modes (e.g. single scan or multi scan)

| Description   | Value           |
| ------------- | --------------- |
| Default       | `SINGLE`        |
| Example       | `MULTI`         |
| Unit          | -               |
| Allowed Range | SINGLE or MULTI |
| Dependencies  | -               |

### BallSize

The size of the ball moving between PassObjectives

| Description   | Value                    |
| ------------- | ------------------------ |
| Default       | `0.5`                    |
| Example       | `0.5`                    |
| Unit          | m                        |
| Allowed Range | any floatingpoint number |
| Dependencies  | -                        |

Technical information: `PassController.Initiate`

### DifficultyRank

Unused.

### LeftStartPassObjective

Start position of the left PassObjective (initial pass giver) as (x/y/z) Coordinate.

| Description   | Value                                                                                       |
| ------------- | ------------------------------------------------------------------------------------------- |
| Default       | `(-8/3.5/15)`                                                                               |
| Example       | `(-8/3.5/15)`                                                                               |
| Unit          | (m/m/m) center is (0/0/0)                                                                   |
| Allowed Range | no restrictions                                                                             |
| Dependencies  | It should consider defined position for [RightStartPassObjective](#RightStartPassObjective) |

Technical information: `PassController.Initiate`

### RightStartPassObjective

Start position of the right PassObjective (initial pass receiver) as (x/y/z) Coordinate.

| Description   | Value                                                                                     |
| ------------- | ----------------------------------------------------------------------------------------- |
| Default       | `(8/3.5/15)`                                                                              |
| Example       | `(8/3.5/15)`                                                                              |
| Unit          | (m/m/m) center is (0/0/0)                                                                 |
| Allowed Range | no restrictions                                                                           |
| Dependencies  | It should consider defined position for [LeftStartPassObjective](#LeftStartPassObjective) |

Technical information: `PassController.Initiate`

### MaxLeftPositionPassObjective

Positioning PassObjectives randomly, this is the most left position possible

| Description   | Value                                                                      |
| ------------- | -------------------------------------------------------------------------- |
| Default       | `-15`                                                                      |
| Example       | `-12.5`                                                                    |
| Unit          | m                                                                          |
| Allowed Range | `-15` to `-30`                                                             |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked |

Technical information: `PassController.DetermineNextPosition`

### MaxRightPositionPassObjective

Positioning PassObjectives randomly, this is the most right position possible

| Description   | Value                                                                      |
| ------------- | -------------------------------------------------------------------------- |
| Default       | `15`                                                                       |
| Example       | `12.5`                                                                     |
| Unit          | m                                                                          |
| Allowed Range | `15` to `30`                                                               |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked |

Technical information: `PassController.DetermineNextPosition`

### MaxUpperPositionPassObjective

Positioning PassObjectives randomly, this is the most upper position possible

| Description   | Value                                                                                                                   |
| ------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Default       | `4`                                                                                                                     |
| Example       | `3.25`                                                                                                                  |
| Unit          | m                                                                                                                       |
| Allowed Range | `1` to `7`                                                                                                              |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere MinLowerPositionPassObjective |

Technical information: `PassController.DetermineNextPosition`

### MinLowerPositionPassObjective

Positioning PassObjectives randomly, this is the lowest position possible

| Description   | Value                                                                                                                                                     |
| ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `4`                                                                                                                                                       |
| Example       | `3.25`                                                                                                                                                    |
| Unit          | m                                                                                                                                                         |
| Allowed Range | `1` to `7`                                                                                                                                                |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere [MaxUpperPositionPassObjective](#MaxUpperPositionPassObjective) |

Technical information: `PassController.DetermineNextPosition`

### MaxNearPositionPassObjective

Positioning PassObjectives randomly, this is the nearest position possible

| Description   | Value                                                                                                                                                 |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `10`                                                                                                                                                  |
| Example       | `15.25`                                                                                                                                               |
| Unit          | m                                                                                                                                                     |
| Allowed Range | `10` to `30`                                                                                                                                          |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere [MaxFarPositionPassObjective](#MaxFarPositionPassObjective) |

Technical information: `PassController.DetermineNextPosition`

### MaxFarPositionPassObjective

Positioning PassObjectives randomly, this is the farest position possible

| Description   | Value                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `25`                                                                                                                                                    |
| Example       | `10.25`                                                                                                                                                 |
| Unit          | m                                                                                                                                                       |
| Allowed Range | `10` to `30`                                                                                                                                            |
| Dependencies  | Relevant if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere [MaxNearPositionPassObjective](#MaxNearPositionPassObjective) |

Technical information: `PassController.DetermineNextPosition`

### WeatherEffect

Applies a weather effect during gameplay

| Description   | Value                                  |
| ------------- | -------------------------------------- |
| Default       | -                                      |
| Example       | `rain`                                 |
| Unit          | -                                      |
| Allowed Range | `rain` to `fog` (case does not matter) |
| Dependencies  |                                        |

### WeatherIntensity

The intensity of the weather effect applied during gameplay

| Description   | Value                                                  |
| ------------- | ------------------------------------------------------ |
| Default       | `0.0`                                                  |
| Example       | `0.5`                                                  |
| Unit          | -                                                      |
| Allowed Range | `0.0` to `1.0`                                         |
| Dependencies  | Relevant if [WeatherEffect](#WeatherEffect) is defined |

### EnableSupporters

If checked, [TeamSupportersRatio](#TeamSupportersRatio) and [OpponentSupportersRatio](#OpponentSupportersRatio) are applied and supporters are rendered according to the definition there.

| Description   | Value         |
| ------------- | ------------- |
| Default       | `false`       |
| Example       | check         |
| Unit          | boolean value |
| Allowed Range | -             |
| Dependencies  | -             |

### TeamSupportersRatio

Defines how many team supporters will be rendered within the stadion.
0 means no team supporters 1 means the max. number of team supporters.

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `0.0`                                                        |
| Example       | `0.985`                                                      |
| Unit          | -                                                            |
| Allowed Range | `0.0` - `1.0`                                                |
| Dependencies  | Relevant if [EnableSupporters](#EnableSupporters) is checked |

### OpponentSupportersRatio

Defines how many opponent supporters will be rendered within the stadion.
0 means no opponent supporters 1 means the max. number of opponent supporters.

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `0.0`                                                        |
| Example       | `0.985`                                                      |
| Unit          | -                                                            |
| Allowed Range | `0.0` - `1.0`                                                |
| Dependencies  | Relevant if [EnableSupporters](#EnableSupporters) is checked |

## Passes

Table contains parameters to describe passes. Each row defines a single pass.

### Id

A pass identifier. Used to reference pass within the PassLoops table ([AssignedToPassId](#AssignedToPassId)). Auto increments.

| Description   | Value                                 |
| ------------- | ------------------------------------- |
| Default       | Pass-n                                |
| Example       | Pass-0001                             |
| Unit          | -                                     |
| Allowed Range | -                                     |
| Dependencies  | [AssignedToPassId](#AssignedToPassId) |

Technical information: `Lib-Exercises`

### BallSpeed

Ball speed in meter per second.

| Description   | Value             |
| ------------- | ----------------- |
| Default       | `0`               |
| Example       | `3`               |
| Unit          | m/s               |
| Allowed Range | any integer value |
| Dependencies  | -                 |

Technical information: `PassController.PlayPass`

### PassGiverTarget

Deterministic target position of the PassObjective (pass giver) as (x/y/z) Coordinate.
Note that with each row the PassGiver changes, because the PassReceiver becomes the PassGiver in the next pass.

| Description   | Value                                                                                  |
| ------------- | -------------------------------------------------------------------------------------- |
| Default       | `(8/3.5/15)`                                                                           |
| Example       | `(-2/2.5/10)`                                                                          |
| Unit          | (m/m/m) center is (0/0/0)                                                              |
| Allowed Range | no restrictions                                                                        |
| Dependencies  | Only applies if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is **not** checked |

Technical information: `PassController.DetermineNextPosition`

### IsRandomPassGiverTarget

Defines whether PassObjective (pass giver) should have a random target position. If checked PassGiverTarget is ignored.

| Description   | Value                                                                                           |
| ------------- | ----------------------------------------------------------------------------------------------- |
| Default       | `false`                                                                                         |
| Example       | check                                                                                           |
| Unit          | boolean value                                                                                   |
| Allowed Range | -                                                                                               |
| Dependencies  | Enables random target positioning and **disables** [PassGiverTarget](#PassGiverTarget) position |

Technical information: `PassController.DetermineNextPosition`

### PassGiverTargetMinDistance

Min distance of pass giver target position from pass receiver position (next loop pass giver). Relevant in combination with random positioning.

Note that the program tries to find a random target postion within the boundries of [PassGiverTargetMinDistance](#PassGiverTargetMinDistance) and [PassGiverTargetMaxDistance](#PassGiverTargetMaxDistance) in cycles. If a target positon can not be found within **200** cycles, the best target position found within those cycles is chosen (best means: target position with maximum distance).

| Description   | Value                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `8`                                                                                                                                                     |
| Example       | `8.25`                                                                                                                                                  |
| Unit          | m                                                                                                                                                       |
| Allowed Range | `8` to `20`                                                                                                                                             |
| Dependencies  | Only applies if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere [PassGiverTargetMaxDistance](#PassGiverTargetMaxDistance) |

Technical information: `PassController.DetermineNextPosition`

### PassGiverTargetMaxDistance

Max distance of pass giver target position from pass receiver position (next loop pass giver). Relevant in combination with random positioning.

For more information see [PassGiverTargetMinDistance](#PassGiverTargetMinDistance).

| Description   | Value                                                                                                                                                   |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `20`                                                                                                                                                    |
| Example       | `16.25`                                                                                                                                                 |
| Unit          | m                                                                                                                                                       |
| Allowed Range | `8` to `20`                                                                                                                                             |
| Dependencies  | Only applies if [IsRandomPassGiverTarget](#IsRandomPassGiverTarget) is checked; may interfere [PassGiverTargetMinDistance](#PassGiverTargetMinDistance) |

Technical information: `PassController.DetermineNextPosition`

### HasRandomLoops

Defines whether random loops should be generated for this pass.
If checked, [PassLoops](#PassLoops) are ignored for this pass.

| Description   | Value         |
| ------------- | ------------- |
| Default       | `false`       |
| Example       | check         |
| Unit          | boolean value |
| Allowed Range | -             |
| Dependencies  | -             |

Technical information: `RandomLoopGenerator`

### HapticConstraintProbability

Probability that haptic is constraint in the loops randomly generated for this pass.
0.0 means 0% chance, 1.0 means 100% chance.

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `0`                                                          |
| Example       | `0.25`                                                       |
| Unit          | -                                                            |
| Allowed Range | `0.0` to `1.0`                                               |
| Dependencies  | Only applies if [HasRandomLoops](#HasRandomLoops) is checked |

Technical information: `RandomLoopGenerator`

## PassLoops

Table contains parameters to describe loops. Each row defines a single loop.

### AssignedToPassId

Reference to [Pass Id](#Id). Assigns the loop to a pass.

| Description   | Value          |
| ------------- | -------------- |
| Default       | -              |
| Example       | Pass-0001      |
| Unit          | -              |
| Allowed Range | -              |
| Dependencies  | [Pass Id](#Id) |

Technical information: `Lib-Exercises`

### IsHandConstrained

DEPRECATED // not used anymore (only used during level hash calculation)

Defines whether input triggers (balls in front of the player) should be assigned a random hand side.
If assigned to a hand side it is only allowed to hit the input trigger with that randomly assigend hand side.

| Description   | Value         |
| ------------- | ------------- |
| Default       | `false`       |
| Example       | check         |
| Unit          | boolean value |
| Allowed Range | -             |
| Dependencies  | -             |

Technical information: `ColorInputSystem.SetHandConstrainState`

### IsHapticConstrained

Defines whether input triggers (balls in front of the player) can only be hit with a certain hand (if checked, randomly chosen hand controller vibrates in the beginning of the loop).

| Description   | Value         |
| ------------- | ------------- |
| Default       | `false`       |
| Example       | check         |
| Unit          | boolean value |
| Allowed Range | -             |
| Dependencies  | -             |

Technical information: `GameplayController.StartNextLoop`

### ExpectedHandSide

The hand to which the haptic input is restricted.

`r` = right hand; `l` = left hand

| Description   | Value                                                             |
| ------------- | ----------------------------------------------------------------- |
| Default       | Random `r` or `l`                                                 |
| Example       | `r`                                                               |
| Unit          | -                                                                 |
| Allowed Range | `r` to `l`                                                        |
| Dependencies  | Relevant if [IsHapticConstrained](#IsHapticConstrained) is `true` |

Technical information: `LoopPlayer`

### RelevantForEvaluation

Arbitrary string that has no effect on the gameplay. The string will be added to the loop statistics of the specific loop.

| Description   | Value      |
| ------------- | ---------- |
| Default       | `<empty>`  |
| Example       | `MOVEMENT` |
| Unit          | -          |
| Allowed Range | -          |
| Dependencies  | -          |
