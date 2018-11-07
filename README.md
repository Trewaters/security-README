# "security-README", proposed standard for open source repos

version 0.1.0

I am modifying an idea that was proposed here ( https://github.com/securitytxt/security-txt ). I am making a template and guidelines for the `security.md` ReadMe file. Basically designers should still create a "security text file" and place it in the `/.well-known/` directory but the Policy `.html` should point to this `security.md` file if it is an open-source project. 

My hope is it will improve reporting and fixing vulnerabilities when they are discovered. It is something I think should be in all open source commits from day one.

## Getting Started
- "verbose", `security.md` has all the definitions and descriptions of what I propose.
- "tl;dr", `./TEMPLATES/security.md` is a copy and paste for those that just want to get up and running.

### What the app should do?
This is a prosposed standard. If it is not used it should at least provide guidelines on how to deal with responsible security disclosures in the future.

## CREDIT
- Development of the `security.txt ` draft takes place on Github at: https://github.com/securitytxt/security-txt
- [Bishop Fox - Cybersecurity Style Guide - v1.1] (https://www.bishopfox.com/blog/2018/02/hello-world-introducing-the-bishop-fox-cybersecurity-style-guide/)

## Contributing

Solo project so far. Code and graphic design contributors are welcome and encouraged to help. Please read [CONTRIBUTING.md]https://github.com/Trewaters/security-README/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to me. 

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/BART-CLI/project/tags).

## Authors

- **Tre' Grisby** - _Initial work_ - [@trewaters on github](https://github.com/trewaters)

See below the list of contributors who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

- "I tip my hat to anyone whose code was used!" npm gives me a lot of people to thank!
- Special thank you to my mom, wife, and daughter! Without their love and support this would gone nowhere.
- Gratitude is the attitude!

#### NOTES
**Timeline:** 
- This all started on November 1, 2018 when I gave a talk at SFNode titled "Node.js Security best practices". I asked everyone to start using a `security.md` file in their open source projects. Then I realized such a specification didn't actually exist. So I started one by modifying the current `security.txt` specs, and here we are.
- On November 4th this was committed to the Node.js foundation [see commit here...](https://github.com/nodejs/node/commit/472a3d890bcd1c6799658d72bb813626a16d0adc)