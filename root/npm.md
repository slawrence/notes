1. bump the version in your `package.json` file.
2. add release notes to README if any
3. stage the package.json file's change.
4. commit that change with a message like "release 0.6.22".
5. create a new git tag for the release. (git tag v#.#.#)
6. push the changes out to github.
7. also push the new tag out to github. (git push origin v#.#.# or git push origin --tags for all)
8. publish the new version to npm. (npm publish)
