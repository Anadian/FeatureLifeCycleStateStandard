# Feature Life Cycle State Standard
v0.0.1
## Preamble
This is a list of keywords, and their associated meaning, for describing the development and maintenance status of functions and features in public APIs. 
I created this "standard" because, as far as I'm aware, no existing standard has been created for such things: believe me. This list is based of common terms I've often seen used in existing documentation to describe status of new, experimental, stable, and deprecated features from conception to removal. The use of key words "MUST", "SHOULD" and "MAY" in this standard are in accordance with their definitions in [RFC  2119](https://tools.ietf.org/html/rfc2119)
## Lifecycle-State Keywords
1. **Planning**: This proposed feature exists in a purely conceptually state and is merely being consider for future implementation; use this keyword to denote features you plan on adding eventually or are currently hearing suggestions or concerns on before reserving any names for it in your code or API.
2. **Reserved**: This feature/function is named and reserved for future implementation but without any working implementation at the present time.
3. **WIP**: Work in Progress: work has begone to implement this feature but is not in a shippable, not even for a developmental build, or tested state.
4. **Experimental**: The feature/function is implemented, in theory, but is still being tested and debugged and, as such, has a decent causing of causing unexpected errors.
5. **Stable**: The feature/function is implemented, tested, and fully documented; developers SHOULD be able to use this feature with confidence that it will work as intended and not be changed without warning.
6. **Deprecated**: This feature is being "sunset" but SHOULD still work as originally intended. This feature is no longer recommended for new developers; it may be made Obsolete or continue to exist purely for legacy support and backwards compatibility. Documentation SHOULD be updated to direct developers to the API or function they should use instead.
7. **Obsolete**: Denotes that a feature will be **removed** in a coming update; code depending on this must be changed else breaking and unsupported behaviour is expected. The function MAY also be altered to warn that it is obsolete and should not be relied upon anymore. The feature/functions newly denoted with this keyword SHOULD always have had **at least** one update in which they were tagged as Deprecated.
8. **Removed**: Denotes a feature has been removed completely and will not be present in the current version onwards. Removed features and functions SHOULD always have **at least** one update in which they're tagged as Obsolete before reaching this state.

## Additional Keywords
Occasionally, it can be convenient to compound multiple keywords into a single keyword, for such instances additional non-numbered keywords can be added here:
- **Introduced**: When starting a new project, you may create several basic functions for your software before even your first commit so the Introduced keyword was added denote a function has having been introduced in a version as WIP skipping past a Planning or Reserved version.
## Usage
You can use either the index numbers or the keywords themselves to denote the state of a feature/function but using the the words themselves is recommended has they convey semantic meaning even to people unfamiliar with this standard.
Additionally, these state keywords work great for tracking change history for functions; for example, a function's documentation may include the following markdown table:
```md
Status:
| version | status |
| --- | --- |
| 4.0.0 | Removed |
| 3.3.0 | Obsolete |
| 3.2.1 | Deprecated |
| 0.0.7 | Stable |
| 0.0.5 | Experimental |
| 0.0.4 | WIP |
| 0.0.3 | Reserved |
| 0.0.1 | Planning |
```
State keywords can also be placed one after another to indicate a function has having passed multiple sections in a single version update; for example:
```md
Status:
| version | status |
| --- | --- |
| 0.0.3 | WIP, Experimental |
| 0.0.2 | Planned, Reserved |
```
would indicate the function was both planned and reserved between the release of v0.0.1 and v0.0.2 and was implemented to the point of being runnable between the release of v0.0.2 and v0.0.3.
## Contributing
Finally, this draft is still being updated and all feedback, suggestions, amendments, and formalisations are appreciated. My goal is to have this be a useful reference point for writing any sort of technical documentation so, if you don't find this document useful, please tell me why, through a [GitHub issue](https://github.com/Anadian/FeatureLifeCycleStateStandard/issues), or make some changes, via a [Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests), with what you think would improve it. 

