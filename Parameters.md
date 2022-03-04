# Level Design Parameters Documentation

## Table of Content

- [Settings Table](#Settings)
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
- [Passes Table](#Passes)
  - [BallSize](#Id)
  - [BallSpeed](#BallSpeed)
  - [PassGiverTarget](#PassGiverTarget)
  - [IsRandomPassGiverTarget](#IsRandomPassGiverTarget)
  - [PassGiverTargetMinDistance](#PassGiverTargetMinDistance)
  - [PassGiverTargetMaxDistance](#PassGiverTargetMaxDistance)
  - [HasRandomLoops](#HasRandomLoops)
  - [PlayerRangeLeft (Pass)](#PlayerRangeLeft_Pass)
  - [PlayerRangeRight (Pass)](#PlayerRangeRight_Pass)
  - [StalemateProbability](#StalemateProbability)
  - [WithPlayersMovement](#WithPlayersMovement)
  - [WithStalemateMovement](#WithStalemateMovement)
- [PassLoops Table](#PassLoops)
  - [AssignedToPassId](#AssignedToPassId)
  - [IsScanPlayersSituation](#IsScanPlayersSituation)
  - [PlayerRangeLeft](#PlayerRangeLeft)
  - [PlayerRangeRight](#PlayerRangeRight)
  - [PlayersSituationDistance](#PlayersSituationDistance)
  - [PlayersSituationRadius](#PlayersSituationRadius)
  - [PlayersMinDistanceBetween](#PlayersMinDistanceBetween)
  - [MatesOpponentsRatio](#MatesOpponentsRatio)
  - [MatePredefinedPlaces](#MatePredefinedPlaces)
  - [OpponentPredefinedPlaces](#OpponentPredefinedPlaces)
  - [IsHandConstrained](#IsHandConstrained)
  - [IsHapticConstrained](#IsHapticConstrained)
  - [IsStalemateSituationPresent](#IsStalemateSituationPresent)
  - [StalemateRangeLeft](#StalemateRangeLeft)
  - [StalemateRangeRight](#StalemateRangeRight)
  - [StalemateSituationDistance](#StalemateSituationDistance)
  - [StalemateSituationRadius](#StalemateSituationRadius)
  - [StalematePinsPerTeam](#StalematePinsPerTeam)
  - [StalemateMinDistanceBetween](#StalemateMinDistanceBetween)
  - [StalemateMatePredefinedPlaces](#StalemateMatePredefinedPlaces)
  - [StalemateOpponentPredefinedPlaces](#StalemateOpponentPredefinedPlaces)
  - [RelevantForEvaluation](#RelevantForEvaluation)

# Parameters

## Settings

Table contains parameters that belong to the whole Level.

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

### PlayerRangeLeft_Pass

see [PlayerRangeRight](#PlayerRangeRight)

with the difference that here, it is applied to all loops randomly generated for this pass.
Only applies if [HasRandomLoops](#HasRandomLoops) is checked.

### PlayerRangeRight_Pass

see [PlayerRangeRight](#PlayerRangeRight)

with the difference that here, it is applied to all loops randomly generated for this pass.
Only applies if [HasRandomLoops](#HasRandomLoops) is checked.

### StalemateProbability

Probability that a random Stalemate situation is shown in the loops randomly generated for this pass.
0.0 means 0% chance, 1.0 means 100% chance.

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `0`                                                          |
| Example       | `0.25`                                                       |
| Unit          | -                                                            |
| Allowed Range | `0.0` to `1.0`                                               |
| Dependencies  | Only applies if [HasRandomLoops](#HasRandomLoops) is checked |

Technical information: `RandomLoopGenerator`

### WithPlayersMovement

Enables random movement of humanoids within players situation.

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `false`                                                      |
| Example       | check                                                        |
| Unit          | boolean value                                                |
| Allowed Range | -                                                            |
| Dependencies  | Only applies if [HasRandomLoops](#HasRandomLoops) is checked |

Technical information: `HumPlacement`

### WithStalemateMovement

Enables random movement of humanoids within stalemate situation

| Description   | Value                                                        |
| ------------- | ------------------------------------------------------------ |
| Default       | `false`                                                      |
| Example       | check                                                        |
| Unit          | boolean value                                                |
| Allowed Range | -                                                            |
| Dependencies  | Only applies if [HasRandomLoops](#HasRandomLoops) is checked |

Technical information: `HumPlacement`

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

### IsScanPlayersSituation

Defines whether PlayersSituation should be rendered within that loop.

| Description   | Value                    |
| ------------- | ------------------------ |
| Default       | `false`                  |
| Example       | check                    |
| Unit          | boolean value            |
| Allowed Range | -                        |
| Dependencies  | Enables PlayersSituation |

Technical information: `GameplayController.StartNextLoop`

### PlayerRangeLeft

A value or a value range that defines where the PlayersSituation appears at the left side of the player.

The determination of the PlayersSituation appearance angle is based on [PlayerRangeLeft](#PlayerRangeLeft) and PlayerRangeRight[PlayerRangeRight](#PlayerRangeRight).

- If there are configs for both sides, the configuration is randomly chosen.
- If there is a config for only one side, the configuration is chosen.
- If there is no (valid) configuration, the angle is chosen randomly.

| Description   | Value                                                                                                                                           |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `0-180`                                                                                                                                         |
| Example       | `10` or `10-50`                                                                                                                                 |
| Unit          | degrees                                                                                                                                         |
| Allowed Range | `0` to `180`                                                                                                                                    |
| Dependencies  | If [PlayerRangeLeft](#PlayerRangeLeft) and PlayerRangeRight[PlayerRangeRight](#PlayerRangeRight) are defined, one definition is picked randomly |

Technical information: `AngleDetermination`

### PlayerRangeRight

A value or a value range that defines where the PlayersSituation appears at the right side of the player.

For more information see [PlayerRangeLeft](#PlayerRangeLeft).

| Description   | Value                                                                                                                                           |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `0-180`                                                                                                                                         |
| Example       | `10` or `10-50`                                                                                                                                 |
| Unit          | degrees                                                                                                                                         |
| Allowed Range | `0` to `180`                                                                                                                                    |
| Dependencies  | If [PlayerRangeLeft](#PlayerRangeLeft) and PlayerRangeRight[PlayerRangeRight](#PlayerRangeRight) are defined, one definition is picked randomly |

Technical information: `AngleDetermination`

### PlayersSituationDistance

The distance between the center of the PlayersSituation and the center of the game (where the player is roughly located).

| Description   | Value                             |
| ------------- | --------------------------------- |
| Default       | Random value within allowed range |
| Example       | `4.25`                            |
| Unit          | m                                 |
| Allowed Range | `4` to `30`                       |
| Dependencies  | -                                 |

Technical information: `PlayersSituationIsland.Place`

### PlayersSituationRadius

The radius in which Pins are distributed around the center of the PlayersSituation. Only relevant if Pins are not predefined.

| Description   | Value                                                                                                                                  |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `3.25`                                                                                                                                 |
| Example       | `5`                                                                                                                                    |
| Unit          | degrees                                                                                                                                |
| Allowed Range | `1` to `20`                                                                                                                            |
| Dependencies  | Only applies if both [MatePredefinedPlaces](#MatePredefinedPlaces) and [OpponentPredefinedPlaces](#OpponentPredefinedPlaces) are empty |

Technical information: `PlayersSituationIsland.PlacePinsRandomly`

### PlayersMinDistanceBetween

Minimum distance between Pins on a PlayersSituation. Note that it depends on the radius, whether the distance can be achieved.

The island might be too small to render all pins without overlapping. The implemented solution will allow overlapping if the island is too small.
To decide whether overlapping is allowed, simplicity is calculated based on the following formula:

`simplicity = island radius / (number of pins * required distance)`

If `simplicity < 1.8`, overlapping is allowed.
With the current max size of the island (`3,25`), it is not possible to render `19` pins without overlapping. It is not even possible with a min distance of < `0,2`.
According to the formula above, `9` pins is the max rendered with a min distance of `0,2`.

`3,25/(9*0,2)= 1,8055555556`

| Description   | Value                                                                               |
| ------------- | ----------------------------------------------------------------------------------- |
| Default       | `0.2`                                                                               |
| Example       | `5`                                                                                 |
| Unit          | m                                                                                   |
| Allowed Range | `0.2` to `10`                                                                       |
| Dependencies  | [PlayersSituationRadius](#PlayersSituationRadius) and number of Pins to be rendered |

Technical information: `UniquePlaces.Generate`

### MatesOpponentsRatio

The ratio of mate and opponent Pins shown on the PlayersSituation.

| Description   | Value                                                                                                                                                                                                                     |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | `0:0`                                                                                                                                                                                                                     |
| Example       | `5:1`                                                                                                                                                                                                                     |
| Unit          | ratio                                                                                                                                                                                                                     |
| Allowed Range | `<0-10>:<0-10>`                                                                                                                                                                                                           |
| Dependencies  | Note that even if places are predefined [MatePredefinedPlaces](#MatePredefinedPlaces) and [OpponentPredefinedPlaces](#OpponentPredefinedPlaces) the ratio must match the predefined ratio for correct evaluation reasons. |

Technical information: `PlayersSituationIsland.PlacePinsRandomly`

### MatePredefinedPlaces

Explicit placement of mate pins around the center of the PlayersSituation as (x/z) Coordinates.
E.g.: `(0.0/0.0);(1.0/1.0)`

In addition to static placement, it is possible to define movements following the pattern: `(x/z)=durationA>(x/z)`.
E.g.: `(1.1/1.1)=1.0>(3.5/3.5)=2.1>(1.6/1.6);(1.4/2.2)=1.0>(-4.6/-2.8)`

| Description   | Value                                                                                                                 |
| ------------- | --------------------------------------------------------------------------------------------------------------------- |
| Default       | -                                                                                                                     |
| Example       | `(1.1/1.1)=1.0>(3.5/3.5)=2.1>(1.6/1.6);(1.4/2.2)`                                                                     |
| Unit          | (m/m) center of the PlayersSituation is (0/0)                                                                         |
| Allowed Range | no restrictions                                                                                                       |
| Dependencies  | Note that [MatesOpponentsRatio](#MatesOpponentsRatio) must match the predefined ratio for correct evaluation reasons. |

Technical information: `PredefinedPositioning`

### OpponentPredefinedPlaces

Explicit placement of opponent pins around the center of the PlayersSituation.

see [MatePredefinedPlaces](#MatePredefinedPlaces)

### IsHandConstrained

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

### IsStalemateSituationPresent

Defines whether a StalemateSituation should be rendered in addition to the PlayersSituation.

| Description   | Value         |
| ------------- | ------------- |
| Default       | `false`       |
| Example       | check         |
| Unit          | boolean value |
| Allowed Range | -             |
| Dependencies  | -             |

Technical information: `GameplayController.RenderPlayersSituations`

### StalemateRangeLeft

see [PlayerRangeLeft](#PlayerRangeLeft)

In addition to the way the [PlayerRange](#PlayerRangeLeft) works the StalemateSituation is shown in the opposite of the PlayersSituation if [StalemateRangeLeft](#StalemateRangeLeft) and [StalemateRangeRight](#StalemateRangeRight) are left empty.

### StalemateRangeRight

see [PlayerRangeRight](#PlayerRangeRight)
and [StalemateRangeLeft](#StalemateRangeLeft)

### StalemateSituationDistance

see [PlayersSituationDistance](#PlayersSituationDistance)

### StalemateSituationRadius

see [PlayersSituationRadius](#PlayersSituationRadius)

### StalematePinsPerTeam

A StalemateSituation always consists of an equal number of mate and opponent Pins. This parameter defines how many Pins per team show up.

| Description   | Value                                                                                                                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | Random value within allowed range                                                                                                                                                                                             |
| Example       | `2`                                                                                                                                                                                                                           |
| Unit          | -                                                                                                                                                                                                                             |
| Allowed Range | `1` to `5`                                                                                                                                                                                                                    |
| Dependencies  | Ignored if pins are predefined: [StalemateMatePredefinedPlaces](#StalemateMatePredefinedPlaces) and [StalemateOpponentPredefinedPlaces](#StalemateOpponentPredefinedPlaces). In that case you must ensure stalemate property. |

Technical information: `GameplayController.RenderPlayersSituations`

### StalemateMinDistanceBetween

see [PlayersMinDistanceBetween](#PlayersMinDistanceBetween)

### StalemateMatePredefinedPlaces

see [MatePredefinedPlaces](#MatePredefinedPlaces)

### StalemateOpponentPredefinedPlaces

see [OpponentPredefinedPlaces](#OpponentPredefinedPlaces)

### RelevantForEvaluation

Arbitrary string that has no effect on the gameplay. The string will be added to the loop statistics of the specific loop.

| Description   | Value      |
| ------------- | ---------- |
| Default       | `<empty>`  |
| Example       | `MOVEMENT` |
| Unit          | -          |
| Allowed Range | -          |
| Dependencies  | -          |
