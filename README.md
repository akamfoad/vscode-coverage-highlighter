<h1 style="border-bottom: none;" align="center">
  <br>
    <img src="images/icon.png?raw=true" alt="logo" width="100">
  <br>
  <br>
  Code Coverage Highlighter
</h1>


<p align="center">This is a <a href="https://code.visualstudio.com">Visual Studio Code</a> extension that allows you to see your code coverage.</p>

> badjes here

---

## Who can use it?
Does your project use tests? What about code coverage tool? When your development environment prepares coverage report, this extension will highlight your code fragments.


## Supported formats

This extension supports several code coverage formats. Depending on the format only code lines or certain fragments can be be highlighted.

| Format | Search pattern | Fragments highlighting |
| -- | -- | :--: |
| **LCOV** | `coverage/lcov*.info` | **No** |
| **Istambul** | `coverage/coverage-final.json` | **Yes** |
| **Cobertura** | `cov*.xml` | **No** |


## Highlight examples

Appearance depends on your code coverage format and configuration.


### Code with highlighted fragments

Istambul file is providing fragment highlighting:

<img src="images/code1.png" alt="Code fragments example" width="449">


### Code with highlighted lines

The LCOV format was used there. Only uncovered lines were highlighted. This format doesn't support fragment highlighting:

<img src="images/code2.png" alt="Code lines example" width="449">


### Alternative appearance

You can enable `wholeLine` mode. It will look especially good when your coverage format doesn't support fragments:

<img src="images/code3.png" alt="Code lines with wholeLine option" width="449">


## Status bar

Whereas extension be able to find coverage file, it will add icon to your status bar. There will be average code coverage percentage. Click on eye-icon will switch coverage displaying.

<img src="images/statusbar1.png" alt="Code lines with wholeLine option" width="354">


<!-- : **LCOV** and **Cobertura**. For example, first of them usually uses with projects which are written in JavaScript or TypeScript. And the second with projects written in Python. -->
## Configuration
You can adjust some of the configuration options.

### Coverage report files
The extension will search coverage report files at start. Also it will start file system watcher. When file with target pattern will be changed, this extension will try to read it.

```json
"vscode-coverage-highlighter.files": [
    "coverage/coverage-final.json",
    "coverage/lcov*.info",
    "cov*.xml"
]
```

### Show coverage by-default

When the target files would be found, should extension highlight coverage immediately? Coverage could be hidden instead. Click on eye on status bar will highlight coverage.

```json
"vscode-coverage-highlighter.defaultState": "enable"
```

### Highlight whole line or text only

This is an appearance option. When it is the true, a line will be highlighted wholly. Otherwise, only text will be highlighted.

```json
"vscode-coverage-highlighter.wholeLine": false
```

### The colors 

The extension supports two colors. For covered and uncovered lines. It would be optimal to write colors in rgba notation. Because highlight with alpha channel wouldn't hide the other decorations.

You also can disable one or more colors completely. Just pass empty string for color and decoration won't be shown.

```json
"vscode-coverage-highlighter.colors": {
    "green": "rgba(20, 250, 20, 0.1)",
    "red": "rgba(255, 20, 20, 0.4)"
} 
```


## Commands

Open the `Command Palette` and type `Code Coverage`


- **Toggle coverage display**: When text has been highlighted it will hide highlighting. By clicking on eye on your status bar you can do the same.


## How to contribute

Read the [contribution guidelines](https://github.com/xx/xxx/blob/master/CONTRIBUTING.md).
