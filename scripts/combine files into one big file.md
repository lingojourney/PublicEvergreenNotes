`for /r . %a in (*.md) do type "%a" >> allContents.txt`

`(for /r . %a in (*.md) do @echo %a && type "%a") > all.txt`

`for /r . %a in (*.md) do @(echo %a && type "%a") > all.txt`
# Notes
## `%a` vs `%%a`
I'll clarify the difference between `%a` and `%%a` in the context of batch scripting:

- **`%a`** is used when running a `for` loop directly from the command line. The Windows command line interpreter expects a single `%` to precede the variable name.

- **`%%a`** is used in a batch file. When writing a script in a batch (.bat) file, you need to use double `%%` to escape the `%` character. This is because the batch file processor treats a single `%` as the beginning of a variable name, so a double `%%` is required to indicate that you're referring to a loop variable.

In summary:
- Use `%a` in the command prompt.
- Use `%%a` in a batch file.

This distinction ensures that your loops function correctly in their respective environments.

