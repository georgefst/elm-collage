# Changelog


## [2.0.3](https://github.com/timjs/elm-collage/compare/2.0.2...2.0.3) (2020-12-14)

Only doc changes (thanks to @indique)


## [2.0.2](https://github.com/timjs/elm-collage/compare/2.0.1...2.0.2) (2019-06-07)

### Changed

  - Support opacity for all collage types (thanks to @brainrape)
  - Delete dead code in examples (thanks to @vvv)


## [2.0.1](https://github.com/timjs/elm-collage/compare/2.0.0...2.0.1) (2019-01-14)

### Changed

  - Typo in documentation (@robx)
  - Use [avh4/elm-color](https://github.com/avh4/elm-color) instead of [the-sett/elm-color], as it is intended to become the [next standard](https://github.com/avh4/elm-color/issues/16).
  - Add link to module documentation in README.


## [2.0.0](https://github.com/timjs/elm-collage/compare/1.6.0...2.0.0) (2018-09-03)

  **Updated for Elm 0.19!**

  **Note:** because Elm 0.19 [removed the possibility to use native calls](https://discourse.elm-lang.org/t/native-code-in-0-19/826),
  Elm Collage now reverted to a simplistic width calculation of rendered text.
  [Any ideas to overcome this are welcome!](https://github.com/timjs/elm-collage/issues/36)

### Removed

  - `Collage.Layout.opposite` in favour of `Collage.Layout.facing`

### Changed

  - The fields of `Collage.Layout.Distances` are renamed to avoid name clashes with anchors defined in the same module:
    - `up` => `toTop`
    - `down` => `toBottom`
    - `left` => `toLeft`
    - `right` => `toRight`


## [1.6.0](https://github.com/timjs/elm-collage/compare/1.5.0...1.6.0) (2018-02-04)

### Added

  - You can now shift a collage in the x- or y- direction only by using `shiftX` or `shiftY`
    (thanks to @nikita-volkov)
  - You can pass explicit SVG attributes when rendering a collage by using `Collage.Render.svgExplicit`
    (thanks to @nikita-volkov)


## [1.5.0](https://github.com/timjs/elm-collage/compare/1.4.0...1.5.0) (2017-10-23)

### Added

  - Now you can name parts of your collage and refer to them later!
    - **This is very experimental!**
    - Use `name` to name a collage
    - Use `locate` to locate a point in a named part of a collage
    - Use `connect` to connect points in named parts of a collage
    - Use `names` to query all used names in a collage

## Changed

  - Anchors now calculate a point relative to the internal origin of a given collage (this used to be the negated point)
  - Some internal renames and algorithms to fold collage trees
  - Simplify the Svg renderer


## [1.4.0](https://github.com/timjs/elm-collage/compare/1.3.1...1.4.0) (2017-10-19)

## Added

  - Separate scaling in X and Y directions with `scaleX` and `scaleY` thanks to @danfishgold!

## Changed

  - Refactored workflow example to reuse more code

## Fixed

  - Fixed a bug with Svg rendering where paths automatically get filled with a uniform black color.
    Paths default to have a transparent fill again!
  - Fixed some documentation and extra notes


## [1.3.1](https://github.com/timjs/elm-collage/compare/1.3.0...1.3.1) (2017-10-12)

### Fixed

  - `Collage.opposite` is no subject for depreciation, although the documentation said so


## [1.3.0](https://github.com/timjs/elm-collage/compare/1.2.0...1.3.0) (2017-10-12)

### Added

  - Create rectangles with rounded corners

### Changed

  - Internal changes:
    - Use circles, technically not needed, but eases calculation of envelopes wrt using ellipses
    - Simplify the renderer
      - Speed up by using `(::)` instead of `(++)`
      - Use builtin `foldl` instead of custom build function
      - Remove unused code for gradients and patterns (like id tracking)
      - Use Svg's x and y attributes when generating Html tag instead of transformations

### Fixed

  - Bug that caused miter line caps to render wrong
  - Bug that forgot to take collage attributes into account for impositions


## [1.2.0](https://github.com/timjs/elm-collage/compare/1.1.0...1.2.0) (2017-10-11)

### Added

  - Collage.Layout
    - A `facing` function to calculate the facing direction.
      Will replace `opposite` in the next major version to avoid name clash with `Collage.opposite`
  - Flowchart example
    - Shows modular creation of collages
    - Uses width and height calculations of subelements
  - Table of contents to each exported module

### Deprecated

  - Collage.Layout
    - `opposite` (in favour of `facing`)

### Changed

  - Correct layout rules for line thickness of shapes
    - Keep track of line thickness and correct for it when calculating the envelopes of shapes
    - Idem for paths, but only if the line cap is _not_ flat

### Fixed

  - Rotation of triangle in axis example
  - Description of arguments of dotted styles
  - Rendering of origin and envelope for debugging


## [1.1.0](https://github.com/timjs/elm-collage/compare/1.0.2...1.1.0) (2017-10-11)

### Added

  - Collage.Layout
    - Way to calculate all four envelope distances at once using `distances`
    - Result is a `Distances` record with up, down, right, and left fields
    - `debug` function which shows the envelope _and_ the origin
  - Html example
  - More documentation

### Fixed

  - Direction of rotation, all rotations are now counter clockwise
  - New algorithm to calculate envelopes using distances
    - Fix bug that handled ellipses incorrectly
    - Fix bug that handled groups incorrectly
  - Small optimisation in envelope calculation


## [1.0.2](https://github.com/timjs/elm-collage/compare/1.0.1...1.0.2) (2017-10-10)

### Added

  - More documentation


## [1.0.1](https://github.com/timjs/elm-collage/compare/1.0.0...1.0.1) (2017-10-10)

### Added

  - More documentation


## 1.0.0 (2017-10-10)

Initial release!
