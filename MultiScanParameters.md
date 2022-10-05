# Level Design MultiScan Parameters Documentation

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
- [PassLoops Table](#PassLoops)
  - [AssignedToPassId](#AssignedToPassId)
  - [IsHandConstrained](#IsHandConstrained)
  - [IsHapticConstrained](#IsHapticConstrained)
  - [ExpectedHandSide](#ExpectedHandSide)
  - [RelevantForEvaluation](#RelevantForEvaluation)
- [PassLoops Table MultiScan](#PassLoopsMultiScan)
  - [Situation1 Distance](#Situation1_PlayersSituationDistance)
  - [Situation1 Radius](#Situation1_PlayersSituationRadius)
  - [Situation1 MatePredefinedPlaces](#Situation1_MatePredefinedPlaces)
  - [Situation1 OpponentPredefinedPlaces](#Situation1_OpponentPredefinedPlaces)
  - [Situation2 Distance](#Situation2_PlayersSituationDistance)
  - [Situation2 Radius](#Situation2_PlayersSituationRadius)
  - [Situation2 MatePredefinedPlaces](#Situation2_MatePredefinedPlaces)
  - [Situation2 OpponentPredefinedPlaces](#Situation2_OpponentPredefinedPlaces)
  - [Situation3 Distance](#Situation3_PlayersSituationDistance)
  - [Situation3 Radius](#Situation3_PlayersSituationRadius)
  - [Situation3 MatePredefinedPlaces](#Situation3_MatePredefinedPlaces)
  - [Situation3 OpponentPredefinedPlaces](#Situation3_OpponentPredefinedPlaces)
  - [ShapeArrangement](#ShapeArrangement)
  - [SituationOffsetInDegrees](#SituationOffsetInDegrees)

  

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

### HapticConstraintProbability

Same as [Shared Parameters](./SharedParameters.md#HapticConstraintProbability)

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

## PassLoopsMultiScan

### Situation1_PlayersSituationDistance

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationDistance)

### Situation1_PlayersSituationRadius

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationRadius)

### Situation1_MatePredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#MatePredefinedPlaces)

### Situation1_OpponentPredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#OpponentPredefinedPlaces)

### Situation2_PlayersSituationDistance

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationDistance)

### Situation2_PlayersSituationRadius

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationRadius)

### Situation2_MatePredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#MatePredefinedPlaces)

### Situation2_OpponentPredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#OpponentPredefinedPlaces)

### Situation3_PlayersSituationDistance

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationDistance)

### Situation3_PlayersSituationRadius

Same as [SingleScan Parameters](./SingleScanParameters.md#PlayersSituationRadius)

### Situation3_MatePredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#MatePredefinedPlaces)

### Situation3_OpponentPredefinedPlaces

Same as [SingleScan Parameters](./SingleScanParameters.md#OpponentPredefinedPlaces)

### ShapeArrangement

The arrangement of the shapes that mark the situations in multi scan play mode. The shapes are currently mapped as follows:

* shape1 = Cube
* shape2 = Sphere
* shape3 = Pyramid

"shape3,shape1,shape2" means that the first situation that shows up at the front right side of the player is marked with a cube etc.

| Description   | Value                    |
| ------------- | ------------------------ |
| Default       | Random                   |
| Example       | `shape3,shape1,shape2`   |
| Unit          | -                        |
| Allowed Range | -                        |
| Dependencies  | -                        |

### SituationOffsetInDegrees

The center of the situations may be shifted on the circle around the player. This parameter defines where the first situation appears on that circle (clockwise). For example: 0 means directly in front of the player. 10 defines a 10 degree shift to the right. In the case where the first situation would show up at 10 degrees, the second would be shifted to 130 and the last one to 250.

| Description   | Value                    |
| ------------- | ------------------------ |
| Default       | 0                        |
| Example       | `20`                     |
| Unit          | degrees                  |
| Allowed Range | 0-120                    |
| Dependencies  | -                        |