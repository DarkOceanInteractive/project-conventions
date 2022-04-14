# Project Conventions

Following these project conventions allows for more productive creation and
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
    - [Design Principles](#design-principles)
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

| Common Name   | Example        | Notes  |
| ------------- | ---------------| ------ |
| Pascal-case   | `DesertEagle`  |        |
| Camel-case    | `desertEagle`  |        |
| Snake-case    | `desert_eagle` |        |
| Upper-case    | `DESERTEAGLE`  |        |
| Lower-case    | `deserteagle`  |        |

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

- Each source file should contain only one `public` class
- Source files should be given the name of the `public` class within
- Class contents should be grouped and sorted by the following sections:
    - Constant Fields
    - Static Fields
    - Other Fields
    - Properties
    - Events / Delegates
    - Constructors
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

> **Note**: rules concerning members order may be bypassed if it makes more
sense to order in an other way. For instance, to achieve the desired order of
appearance in the Unity Inspector, or to group properties that are related
together.

Use [Pascal-case](#types-of-naming-conventions) for **Class Names**.

- Always prefix interface names with an `I`
- Always prefix abstract class names with an `A`

Use **Namespaces** to ensure your scoping of items won't conflict with existing
ones from other- or global namespaces. The project should at minimum use the
project name for its namespaces in order to prevent conflicts with imported
third party assets.

All **Public Functions** should have documentation in [the xmldoc format](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/xmldoc/recommended-tags),
containing at least a summary and a description of their parameters and return
value, if any.
```csharp
/// <summary>
/// Fire a gun.
/// </summary>
/// <param name="bulletType">Type of the bullet to fire</param>
/// <returns>True if the gun was able to fire, false if it wasn't for any reason</returns>
public bool Fire(BulletType bulletType)
{
  // Fire the gun
}
```

**Comments** should be used to describe intention, algorithmic overview, and/or
logical flow. The ideal comment allows someone other than the author to
understand a function's intended behavior and general operation.

- Comments should be placed on a separate line, above the code
- Comment text should begin with an uppercase letter
- Insert one space between the comment delimiter and the comment text

Example:
```csharp
// This is a comment
```

For **Spacing**, use a single space after a comma.

Example: `Console.In.Read(myChar, 0, 1);`

- Do not use a space after the parenthesis and function arguments
- Do not use spaces between a function name and parenthesis
- Do not use spaces inside brackets

Variable- and function **modifiers** should be sorted in the following order:

- public
- private
- protected
- internal
- static
- extern
- new
- virtual
- abstract
- sealed
- override
- readonly
- unsafe
- volatile
- async

> **Note**: you can setup your IDE to lint your code using pre-defined rules,
by setting up a [`.editorconfig`](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/code-style-rule-options?view=vs-2017)
file.

Class members should be accessed through the `this` keyword, as this helps with
tracking the scope of each variable used.

Example:
```csharp
this.transform.position = this._startPosition;
```

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
- Always use [Pascal-case](#types-of-naming-conventions) for interfaces and
  classes
- Always prefix private variables with an underscore
- Always prefix boolean variables with a verb such as `is` or `has`.
- All variable names must be clear, unambiguous, and descriptive **nouns**
- Variable names must not be redundant with their context
- Local variable- and function parameter names should not conflict with other
  variables within the same scope (such as class variables, global variables,
  etc.)
- All **Serializable** variables should make use of value ranges if there is
  ever a value that a variable should not be set to

There are many common rules for naming and maintaining **Functions** and **Event
Handlers** within **Classes**.

- All function names should start with verbs
- All function names should be worded in present tense
- All function names should have context as to what they are doing
- All event handler names should start with `On`

### Design Principles

On a side node, a few design principles should be kept in mind while writing
code:

- **[DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) (Don't Repeat
  Yourself)**: avoid repeating yourself, if something has to be written twice or
  more, isolate it in a reusable function or something similar.
- **[KISS](https://en.wikipedia.org/wiki/KISS_principle) (Keep It Simple
  Stupid)**: most systems work best if they are kept simple; simplicity should
  be a key goal in software design. If something gets overcomplicated, take a
  step back and try to see if there isn't a simpler solution or an architecture
  issue in your code.
- **[SOLID](https://en.wikipedia.org/wiki/SOLID)**:
  - **single-responsibility principle**: Every class and function should only
    have one responsability
  - **open–closed principle**: Every class and function should be open for
    extension, but closed for modification
  - **Liskov substitution principle**: Functions that use references to base
    classes must be able to use objects of derived classes without knowing it
  - **interface segregation principle**: Many client-specific interfaces are
    better than one general-purpose, bloated interface
  - **dependency inversion principle**: Depend upon abstractions, not
    implementations

## Assets

Naming conventions also apply to assets, and enable the contributors to manage,
search, parse and maintain the assets with ease.

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

This article references different sources, from which the outstanding ones are
listed below.
- [Unity Style Guide](https://github.com/justinwasilenko/Unity-Style-Guide)
  written by [justinwasilenko](https://github.com/justinwasilenko) (30-03-2022)
