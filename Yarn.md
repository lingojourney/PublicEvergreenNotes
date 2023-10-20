Yarn is a package manager for your code. It allows you to use and share code with other developers from around the world. Yarn does this quickly, securely, and reliably so you don’t ever have to worry. Yarn allows you to use other developers’ solutions to different problems, making it easier for you to develop your software. It was developed in 2016 by Sebastian McKenzie of Meta (formerly Facebook) for the Node.js JavaScript runtime environment[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29).

Yarn is an alternative to the npm package manager and was created as a collaboration of Facebook (now Meta), Exponent (now Expo.dev), Google, and Tilde (the company behind Ember.js) to solve consistency, security, and performance problems with large codebases[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29).

Yarn can install packages from local cache[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29). It binds versions of the package strongly[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29). Yarn uses checksum for ensuring data integrity, while npm uses SHA-512 to check data integrity of the packages downloaded[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29) . Yarn installs packages in parallel, while npm installs one package at a time[1](https://en.wikipedia.org/wiki/Yarn_%28package_manager%29).

To install yarn: `npm install -g yarn`

To install a package with yarn: `yarn add package-name --dev`

You can learn more about Yarn on their official website [2](https://yarnpkg.com/) or on their introduction page [3](https://yarnpkg.com/getting-started/).

## Yarn vs [[Public/NPM]]
Yarn has several advantages over npm. [Yarn supports features like parallel installation and Zero-Install which results in better performance](https://afteracademy.com/blog/npm-vs-yarn/)[1](https://afteracademy.com/blog/npm-vs-yarn/). [It is several times faster than npm as it downloads the packages at incredible speed](https://waverleysoftware.com/blog/yarn-vs-npm/)[2](https://waverleysoftware.com/blog/yarn-vs-npm/). [Yarn caches every package it has downloaded to avoid re-downloading it later when the need arises](https://waverleysoftware.com/blog/yarn-vs-npm/)[2](https://waverleysoftware.com/blog/yarn-vs-npm/). [Yarn offers stability, providing lock down versions of installed packages](https://waverleysoftware.com/blog/yarn-vs-npm/)[2](https://waverleysoftware.com/blog/yarn-vs-npm/).

Even though Yarn has some advantages, the speeds of Yarn and npm, in their last versions, are pretty comparable. So we can’t define a clean winner here [3](https://www.sitepoint.com/yarn-vs-npm/).

[You can learn more about the differences between Yarn and npm on this Stack Overflow thread](https://stackoverflow.com/questions/40027819/when-to-use-yarn-over-npm-what-are-the-differences) [4](https://stackoverflow.com/questions/40027819/when-to-use-yarn-over-npm-what-are-the-differences) or on this blog post [2](https://waverleysoftware.com/blog/yarn-vs-npm/).