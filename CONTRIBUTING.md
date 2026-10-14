## Contributing

Opening an RFC is rather straightforward. You should copy `0000-template.md` from this directory into `rfcs/`. Upon doing so, rename the file to `XXXX-feature-name`; where `XXXX` is the current ordinal number and `feature-name` is your feature's name written in [kebab-case](https://developer.mozilla.org/en-US/docs/Glossary/Kebab_case).

Once your file is ready open it and start filling it out. Remember to use [snake_case](https://developer.mozilla.org/en-US/docs/Glossary/Snake_case) in the `feature` field of the top table. The string itself should be the same as your previous `feature-name`. All of the other fields should be pretty self-explanatory.

Upon finishing writing your file head over to GitHub and open the PR. Use this syntax for the title: `[RFC X] Y`, where `X` is the ordinal number (this time without the zero-padding used in filenames) and `Y` is your feature title, you can generally set it to whatever you like.

For examples of opened RFCs take a look at [RFC 1's PR](https://github.com/Szpontniki/rfcs/pull/1).

And that's it! With this in mind you should be able to easily create a new RFC.
