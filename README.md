# Project Conventions

Following these project conventions allow for more producitve creation and
maintenance as one does not have to re-learn code-styles or structures when
reading through another contributor's code.

## Table of Contents

- [Terminology](#terminology)
    - [Types of Naming Conventions](#types-of-naming-conventions)
- [Project Structure](#project-structure)
    - [Folder Names](#folder-names)
- [Scripts](#scripts)
    - [Class Organization](#class-organization)
    - [Compiling](#compiling)
    - [Variables](#variables)
- [Assets](#assets)
  - [Name Components](#name-components)
    - [Prefabs](#prefabs)
    - [Materials](#materials)
    - [Textures](#textures)
    - [Animations](#animations)
    - [Artificial Intelligence](#artificial-intelligence)
    - [Miscellaneous](#miscellaneous)
- [Article References](#article-references)

## Terminology

### Types of Naming Conventions

| Common Name   | Example                                        | Notes  |
| ------------- | ---------------------------------------------- | ------ |
| Pascal-case   | `DesertEagle`                                  |        |
| Camel-case    | `desertEagle`                                  |        |
| Snake-case    | `desert_eagle`, `Desert_Eagle`, `desert_Eagle` |        |
| Upper-case    | `DESERTEAGLE`                                  |        |
| Lower-case    | `deserteagle`                                  |        |

## Project Structure

We use a structure that benefits the filtering and searchability of the
**Project Window** in **Unity**.

### Folder Names

There are many common rules for naming any folder in the content structure.
- Always use [Pascal-case](#types-of-naming-conventions)
- Never use spaces
- Never use unicode characters
- No redundant names (such as `Assets`, `Meshes`, `Textures`, or `Materials`)

All **Scene** files must belong in a folder Named `Levels`.

All **Reusable Materials or Textures** files must belong in a folder named
`MaterialLibrary`.

## Scripts

We use styling conventions which conform to **Microsoft's C# Standard**.

### Class Organization

There are many common rules for naming and maintaining **Classes** within
**Source Files**.
- Source files should contain only one `public` class
- Source files should be given the name of the `public` class within
- Class contents should be grouped and sorted by the following sections:
    - Constant Fields
    - Static Fields
    - Other Fields
    - Constructors
    - Properties
    - Events / Delegates
    - Lifecycle Methods (such as `Awake`, `OnEnable`, `OnCollission`, or
      `OnDestroy`)
    - Methods
    - Nested Types
- Whenever possible, variables and methods should be sorted by their **Access
  Modifiers**.
    - `public`
    - `internal`
    - `protected`
    - `private`
- Finally, sort alphabetically.

Use **Namespaces** to ensure your scoping of items won't conflict with existing
ones from other- or global namespaces. The project should at minimum use the
project name for its namespaces in order to prevent conflicts with imported
third party assets.

All **Public Functions** should have a summary.
```
/// <summary>
/// Fire a gun
/// </summary>
public void Fire()
{
// Fire the gun.
}
```

**Comments** should be used to describe intention, algorithmic overview, and/or
logical flow. The ideal comment allows someone other than the author to
understand a function's intended behavior and general operation.
- Comments should be placed on a separate line, above the code
- Comment text should begin with an uppercase letter
- Comment text should end with a period
- Insert one space between the comment delimiter and the comment text

For **Spacing**, use a single space after a comma between function arguments.

Example: `Console.In.Read(myChar, 0, 1);`
- Do not use a space after the parenthesis and function arguments
- Do not use spaces between a function name and parenthesis
- Do not use spaces inside brackets

### Compiling
All scripts should compile with **zero warnings** and **zero errors**. Warnings
and errors may quickly cascade into unexpected behavior.

### Variables

There are many common rules for naming and maintaining **Variables** within
**Classes**.
- Always use [Pascal-case](#types-of-naming-conventions) for public, internal,
  and protected variables
- Always use [Camel-case](#types-of-naming-conventions) for private, and local
  variables
- Always use [Pascal-case](#types-of-naming-conventions) for boolean, and enum
  variables.
- Always use [Pascal-case](#types-of-naming-conventions) for interfaces
- Always prefix private variables with an underscore
- Always prefix boolean variables with a verb
- Always prefix interfaces with an `I`
- All non-boolean variable names must be clear, unambiguous, and descriptive
  **nouns**
- Variable names must not be redundant with their context
- All **Serializable** variables should make use of value ranges if there is
  ever a value that a variable should not be set to

There are many common rules for naming and maintaining **Functions** and **Event Handlers** within **Classes**.
- All function names should start with verbs
- All function names should be worded in present tense
- All function names should have context as to what they are doing
- All event handler names should start with `On`

## Assets

Naming conventions also apply to assets, and enable the contributors to manage,
serach, parse and maintain the assets with ease.

### Name Components

All assets should have a **base asset name**, which is prefixed by the **type**
of asset, and suffixed by the **variant** of the asset. The base asset name
represents a logical grouping of related assets.

Any asset that is part of this logical group, follows the standard
`Prefix_BaseAssetName_Variant`.

Always use [Pascal-case](#types-of-naming-conventions) for the base asset name.

#### Prefabs

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

#### Materials

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

#### Textures

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

#### Animations

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

#### Artificial Intelligence

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

#### Miscellaneous

| Asset Type    | Prefix | Suffix | Notes |
| ------------- | ------ | ------ | ----- |
|               |        |        |       |
|               |        |        |       |
|               |        |        |       |

## Article References
This article refereces different sources, from which the outstanding ones are
listed below.
- [Unity Style Guide](https://github.com/justinwasilenko/Unity-Style-Guide)
  written by [justinwasilenko](https://github.com/justinwasilenko) (30-03-2022)
