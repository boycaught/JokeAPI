<div align="center" style="text-align:center">

# The code in this repo moved
The latest source code of JokeAPI lives on my own Git server for now: https://git.sv443.net/sv443/JokeAPI-v2  
  
If you have any issues, please still use this repository on GitHub to submit them.  
For pull requests however, please use the new repo.  

</div>

<br><br><br><br>

# Contributing Guide
This guide will tell you how you can and should contribute to JokeAPI.  
Not following it might cause me to reject your changes but at the very least we will both lose time.  
So please read this guide before contributing. Thanks :)

## Table of Contents:
- [Submitting or editing jokes](#submitting-or-editing-jokes)
- [Contributing to JokeAPI's code](#submitting-code)
- [Submitting a translation](#submitting-translations)
- [Tips and Tricks for contributing](#other-nice-to-know-stuff)

<br><br><br><br>

## Submitting or editing jokes:
If you want to submit or edit jokes, you can find them in the `jokes-xy.json` files in [`data/jokes/`](../data/jokes/)  
To submit your changes, create a pull request. Also make sure to follow the [code contribution instructions.](#submitting-code)  
  
If you want a joke to be edited, re-flagged or deleted, please [submit a new issue here.](https://github.com/Sv443/JokeAPI/issues/new?assignees=Sv443&labels=joke+edit&template=3_edit_a_joke.md)  
Keep in mind that deleting jokes will be my last resort. I will also not remove jokes based on certain world views and opinions to uphold the API's main purpose; to provide jokes for everyone's taste.  
<!-- TODO: provide source of dark jokes, since this is fully transparent and open source software -->

<br><br>

## Submitting code:
1. [Read the Code_of_Conduct.md file](./Code_of_Conduct.md) (TLDR: just behave in a friendly manner).
2. Fork the repository. Afterwards, clone or download it and locate the folder where it is contained.
3. Make the changes you want to make to the code.
4. Run the script `npm run all` which will run these commands:
    - `npm run validate-jokes` to make sure all jokes are formatted correctly.
    - `npm run validate-ids` to verify that all jokes have the correct ID.
    - `npm run lint` to check the code for any warnings or errors.
    - `npm run dep-graph` to generate a new dependency graph.
    - `npm run generate-changelog` to generate a Markdown changelog out of the plaintext one.
    - `npm run test`, which runs the unit tests for JokeAPI. If you are colorblind, you can run the command `npm run test-colorblind` (will turn green into cyan and red into magenta).
5. Run JokeAPI locally by running the command `node JokeAPI`, request some jokes and test the areas you modified / added to make sure everything still works.
6. Add yourself to the `contributors` object in the [`package.json`](https://git.sv443.net/sv443/JokeAPI-v2/src/main/package.json) file :)
    <!-- - **If it doesn't exist or is empty** please add it using the second format on [this website](https://flaviocopes.com/package-json/#contributors) -->
7. Submit a pull request on your forked repository, selecting `Sv443/JokeAPI` as the base repo and `master` as the base branch and selecting `YourUsername/JokeAPI` as the head repo and `YourBranch` as the compare branch
    - If your pull request is not ready to be merged yet, you can add `[WIP]` to the beginning of the title which will tell the repo maintainer(s) and automated scripts not to merge it yet.
8. Request a review from me (Sv443).
9. Check if the CI script and other checks for your pull request were successful (they can be found below the comments).
    - **If they were unsuccessful:** view the log, fix the errors, commit the code and push to the same branch. This will automatically update your pull request and re-run the checks.
10. Once the pull request is approved and merged, you can delete the source branch and your forked repo if you want to.  
    - **If it isn't**, please read the comments from the reviewer(s) and make the necessary changes.
  
<br><br>

## Submitting Translations:
If you want to submit a translation, please follow these steps:  
1. Find your language's two-character code in the file [`data/languages.json`](https://git.sv443.net/sv443/JokeAPI-v2/src/main/data/languages.json). You'll need to specify it for every translation.
2. Translate coded error messages in the file [`data/errorMessages.js`](https://git.sv443.net/sv443/JokeAPI-v2/src/main/data/errorMessages.js) by following the style of the other translations.
3. Translate the generic strings inside of the file [`data/translations.json`](https://git.sv443.net/sv443/JokeAPI-v2/src/main/data/translations.json) by also following the style of the other translations.
4. Add yourself to the `contributors` object in the [`package.json`](https://git.sv443.net/sv443/JokeAPI-v2/src/main/package.json) file :)

<br><br>

## Other nice-to-know stuff:
- I really recommend using [Visual Studio Code](https://code.visualstudio.com/) with the extension [`fabiospampinato.vscode-highlight`](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-highlight) - it will add custom styling to the syntax highlighting in the editor and make the code easier to read and work with.  
- If you want to generate a dependency graph, you need to install [Graphviz](https://graphviz.gitlab.io/download/) and add the path to the `bin` folder to your `%PATH%` / `$PATH` environment vaiable. Then, run the command `npm run dependency-graph` and open the file [`dev/dependency-graph.html`](../dev/dependency-graph.html) in a browser.  
- If you need to add an authorization token, you can generate one or multiple tokens with the command `npm run add-token [amount]`. If you omit the "amount" parameter, the script will generate a single token. After you run the command, the tokens will be listed in the console and you can now (after restarting JokeAPI) use it in the `Authorization` header to gain unlimited access to JokeAPI [(better explanation here).](https://jokeapi.dev/#api-tokens)  

<br><br>

## If you need any help, feel free to contact me through [Discord](https://sv443.net/discord) (fastest way to contact me) or [E-Mail](mailto:contact@sv443.net?subject=Questions%20about%20contributing%20to%20JokeAPI)
