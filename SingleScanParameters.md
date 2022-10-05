# Level Design SingleScan Parameters Documentation

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
- [Passes Table](#Passes)
  - [BallSize](#Id)
  - [BallSpeed](#BallSpeed)
  - [PassGiverTarget](#PassGiverTarget)
  - [IsRandomPassGiverTarget](#IsRandomPassGiverTarget)
  - [PassGiverTargetMinDistance](#PassGiverTargetMinDistance)
  - [PassGiverTargetMaxDistance](#PassGiverTargetMaxDistance)
  - [HasRandomLoops](#HasRandomLoops)
  - [HapticConstraintProbability](#HapticConstraintProbability)
- [Passes Table SingleScan](#PassesTableSingleScan)
  - [PlayerRangeLeft (Pass)](#PlayerRangeLeft_Pass)
  - [PlayerRangeRight (Pass)](#PlayerRangeRight_Pass)
  - [StalemateProbability](#StalemateProbability)
  - [WithPlayersMovement](#WithPlayersMovement)
  - [WithStalemateMovement](#WithStalemateMovement)
- [PassLoops Table](#PassLoops)
  - [AssignedToPassId](#AssignedToPassId)
  - [IsHandConstrained](#IsHandConstrained)
  - [IsHapticConstrained](#IsHapticConstrained)
  - [ExpectedHandSide](#ExpectedHandSide)
  - [RelevantForEvaluation](#RelevantForEvaluation)
- [PassLoops Table SingleScan](#PassLoopsSingleScan)
  - [IsScanPlayersSituation](#IsScanPlayersSituation)
  - [PlayerRangeLeft](#PlayerRangeLeft)
  - [PlayerRangeRight](#PlayerRangeRight)
  - [PlayersSituationDistance](#PlayersSituationDistance)
  - [PlayersSituationRadius](#PlayersSituationRadius)
  - [PlayersMinDistanceBetween](#PlayersMinDistanceBetween)
  - [MatesOpponentsRatio](#MatesOpponentsRatio)
  - [MatePredefinedPlaces](#MatePredefinedPlaces)
  - [OpponentPredefinedPlaces](#OpponentPredefinedPlaces)
  - [IsStalemateSituationPresent](#IsStalemateSituationPresent)
  - [StalemateRangeLeft](#StalemateRangeLeft)
  - [StalemateRangeRight](#StalemateRangeRight)
  - [StalemateSituationDistance](#StalemateSituationDistance)
  - [StalemateSituationRadius](#StalemateSituationRadius)
  - [StalematePinsPerTeam](#StalematePinsPerTeam)
  - [StalemateMinDistanceBetween](#StalemateMinDistanceBetween)
  - [StalemateMatePredefinedPlaces](#StalemateMatePredefinedPlaces)
  - [StalemateOpponentPredefinedPlaces](#StalemateOpponentPredefinedPlaces)
  - [InputBallArrangement](#InputBallArrangement)

# Shared Parameters

## Settings

Table contains parameters that belong to the whole Level.

### ScanMode

Same as [Shared Parameters](./SharedParameters.md#ScanMode)

### BallSize

Same as [Shared Parameters](./SharedParameters.md#BallSize)

### LeftStartPassObjective

Same as [Shared Parameters](./SharedParameters.md#LeftStartPassObjective)

### RightStartPassObjective

Same as [Shared Parameters](./SharedParameters.md#RightStartPassObjective)

### MaxLeftPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MaxLeftPositionPassObjective)

### MaxRightPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MaxRightPositionPassObjective)

### MaxUpperPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MaxUpperPositionPassObjective)

### MinLowerPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MinLowerPositionPassObjective)

### MaxNearPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MaxNearPositionPassObjective)

### MaxFarPositionPassObjective

Same as [Shared Parameters](./SharedParameters.md#MaxFarPositionPassObjective)

### WeatherEffect

Same as [Shared Parameters](./SharedParameters.md#weathereffect)

### WeatherIntensity

Same as [Shared Parameters](./SharedParameters.md#weatherintensity)


## Passes

Table contains parameters to describe passes. Each row defines a single pass.

### Id

Same as [Shared Parameters](./SharedParameters.md#Id)

### BallSpeed

Same as [Shared Parameters](./SharedParameters.md#BallSpeed)

### PassGiverTarget

Same as [Shared Parameters](./SharedParameters.md#PassGiverTarget)

### IsRandomPassGiverTarget

Same as [Shared Parameters](./SharedParameters.md#IsRandomPassGiverTarget)

### PassGiverTargetMinDistance

Same as [Shared Parameters](./SharedParameters.md#PassGiverTargetMinDistance)

### PassGiverTargetMaxDistance

Same as [Shared Parameters](./SharedParameters.md#PassGiverTargetMaxDistance)

### HasRandomLoops

Same as [Shared Parameters](./SharedParameters.md#HasRandomLoops)

### PlayerRangeLeft_Pass

see [PlayerRangeRight](#PlayerRangeRight)

with the difference that here, it is applied to all loops randomly generated for this pass.
Only applies if [HasRandomLoops](#HasRandomLoops) is checked.

### PlayerRangeRight_Pass

see [PlayerRangeRight](#PlayerRangeRight)

with the difference that here, it is applied to all loops randomly generated for this pass.
Only applies if [HasRandomLoops](#HasRandomLoops) is checked.

### HapticConstraintProbability

Same as [Shared Parameters](./SharedParameters.md#HapticConstraintProbability)

## PassesTableSingleScan

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

Same as [Shared Parameters](./SharedParameters.md#AssignedToPassId)

### IsHandConstrained

Same as [Shared Parameters](./SharedParameters.md#IsHandConstrained)

### IsHapticConstrained

Same as [Shared Parameters](./SharedParameters.md#IsHapticConstrained)

### ExpectedHandSide

Same as [Shared Parameters](./SharedParameters.md#ExpectedHandSide)

### RelevantForEvaluation

Same as [Shared Parameters](./SharedParameters.md#RelevantForEvaluation)

## PassLoopsSingleScan

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

### InputBallArrangement

Defines the arrangement of the input balls (in front of the player) in terms of color order and height.

| Description   | Value                                                                                                                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default       | Random                                                                                                                                                                                  |
| Example       | `c3(0.04),c2(-0.01),c1(0.13)`                                                                                                                                                                                                                           |
| Unit          | the number is in meters above or below the baseline in front of the player                                                                                                                                                                                                                             |
| Allowed Range | number: `-0.1` to `0.15`                                                                                                                                                                                                                    |
| Dependencies  | - |

Technical information: `LoopPlayer` and `ColorInputSystem`