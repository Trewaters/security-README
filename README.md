# "security-README", proposed standard for open source repos
This security ReadMe file, referred to as `SECURITY.md`, is modifying an idea proposed here ( https://github.com/securitytxt/security-txt ). The security ReadMe file creates a template with guidelines for open source projects. If a designer wishes, they could still create a "security text file", referred to as `security.txt`, and place it in the `/.well-known/` directory. Then the security policy (security.policy:"https://example.com/SECURITY.md") should point to this `SECURITY.md` file in an open source project's root directory. The security text file is a standard for applications deployed in the wild that want a machine readable security file. The security ReadMe file is a human readable file for contributors and maintainers that is easy to use.

## What is the  purpose of `SECURITY.md`?
Improve reporting and fixing vulnerabilities when they are discovered. A security ReadMe file should be in all open source commits. It provides guidelines on how to contact projects about security issues, or bugs.

## Getting Started
- "verbose", this `./README.md` has all the definitions and descriptions of what I propose.
- "tl;dr", `./SECURITY.md` is a template which can be copied if you want to get up and running.

1. Create a `security.txt` file. See example below:
```
  # Our security address
  Contact: mailto:security@example.com
  
  # Our PGP key
  Encryption: https://example.com/pgp-key.txt
  
  # Our security policy
  Policy: https://example.com/SECURITY.md
  
  # Our security acknowledgments page
  Acknowledgments: https://example.com/hall-of-fame.html
  
  # Verify this security.txt file
  Signature: https://example.com/.well-known/security.txt.sig
```
2. Create a `SECURITY.md` file. see example below:
```
## Our security policy and Your responsibility
- **POLICY**:
- **SECURITY DISCLOSURE**:
## "MY-PROJECT" Checklist: Security Recommendations
## Version

```
3. Update your security policy of contact information changes. Be vigilant in reviewing and updating this policy as needed.

## Our security policy and Your responsibility
- **POLICY**:
*Our security policy is to avoid leaving the ecosystem worse than we found it. Meaning we are not planning to introduce vulnerabilities into the ecosystem.*

The "MY-PROJECT" team and community take all security bugs in "MY-PROJECT" seriously. Thank you for improving the security of "MY-PROJECT". We appreciate your efforts to disclose the issue responsibly, and will make every effort to acknowledge your contributions.

Report security bugs by emailing the lead maintainer at [EMAIL ADDRESS] and include the word "SECURITY" in the subject line.

The lead maintainer will acknowledge your email within a week (7 days), and will send a more detailed response up to 48 hours after that indicating the next steps in handling your report. After the initial reply to your report, the security team will endeavor to keep you informed of the progress towards a fix and an announcement. We may ask for additional information or guidance.

- "MY-PROJECT" will confirm the problem and determine the affected versions.
- "MY-PROJECT" will audit code to find any similar problems.
- "MY-PROJECT" will prepare fixes for all releases still under maintenance. These fixes will be released as fast as possible.

Report security bugs in third-party modules to the person or team maintaining the module.

- **SECURITY DISCLOSURE**:
*Your responsibility is to report vulnerabilities to us using the guidelines outlined below.*

Please give detailed steps on how to disclose the vulnerability. Keep these OWASP guidelines in mind ( https://www.owasp.org/index.php/Vulnerability_Disclosure_Cheat_Sheet ) when creating your disclosure policy. 

Below are some recommendations for security disclosures:
- "MY-PROJECT" security contact { contact: mailto:[EMAIL ADDRESS] }
- When disclosing vulnerabilities please do the following:
  1. Your name and affiliation (if any).
  2. Include scope of vulnerability. Let us know who could use this exploit.
  3. Document steps to identify the vulnerability. It is important that we can reproduce your findings. 
  4. Show how to exploit vulnerability, give us an attack scenario.

### "MY-PROJECT" Checklist: Security Recommendations
Follow these steps to improve security when using "MY-PROJECT".
1. ...SEE SOMETHING
2. ...SAY SOMETHING

#### 1)...SEE SOMETHING
We suggest you goto #2 if this happens.

**Why?**
Through experience we have found it is best to goto #2 in this situation.

**How?**
Read our suggestions on [Reporting Security Issues](https://github.com/Trewaters/security-README/blob/master/SECURITY.md#our-security-policy-and-your-responsibility).
`SHOW HOW TO CODE EXAMPLES IF POSSIBLE`
or goto #2

## `security.txt` Fields
### **Acknowledgments**
- Definition: This directive allows you to link to a page where security researchers are recognized for their reports.  The page being linked to SHOULD list individuals or companies that disclosed security vulnerabilities and worked with you to remediate the issue.
- Field { Acknowledgments: https://example.com/hall-of-fame.html }
- Example security acknowledgment webpage:
```
  We would like to thank the following researchers:

 (2017-04-15) Frank Denis - Reflected cross-site scripting
 (2017-01-02) Alice Quinn  - SQL injection
 (2016-12-24) John Buchner - Stored cross-site scripting
 (2016-06-10) Anna Richmond - A server configuration issue
```

### **Contact**
- Definition (required): This directive allows you to provide an address that researchers SHOULD use for reporting security issues.  The value MAY be an email address, a phone number and/or a contact page with more information. If this directive indicates a web URL, then it MUST be begin with "https://". The value MUST follow the general syntax described in [RFC3986]. This means that "mailto" and "tel" URI schemes MUST be used when specifying email addresses and telephone numbers. The precedence SHOULD be in listed order.  The first field is the preferred method of contact.
- Field { contact: mailto:trewaters@hotmail.com }
- Example:
```
Contact: mailto:security@example.com
Contact: tel:+1-201-555-0123
Contact: https://example.com/security-contact.html
```

### **Encryption**
- Definition (recommended): This directive allows you to point to an encryption key that security researchers SHOULD use for encrypted communication.  You MUST NOT directly add your key to the field, instead the value of this field MUST be a URI pointing to a location where the key can be retrieved from.  If this directive indicates a web URL, then it MUST be begin with "https://". When it comes to verifying the authenticity of the key, it is always the security researcher's responsibility to make sure the key being specified is indeed one they trust.  Researchers MUST NOT assume that this key is used to generate the signature file
- Field { Encryption: https://example.com/pgp-key.txt }
- Example of a PGP key available from an OPENPGPKEY DNS:
> Encryption: dns:5d2d37ab76d47d36._openpgpkey.example.com?type=OPENPGPKEY
- Example of a PGP key being referenced by its fingerprint:
> Encryption: openpgp4fpr:5f2de5521c63a801ab59ccb603d49de44b29100f

### **Hiring**
- Definition (recommended): The "Hiring" directive is used for linking to the vendor's security-related job positions.  If this directive indicates a web URL, then it SHOULD be begin with "https://".
- Field { Hiring: https://example.com/jobs.html }
- Example: none

### **Permission**
- Definition (required): The presence of the "Permission" directive is used to indicate to security researchers that they MUST NOT perform any kind of testing against the resource hosting the "security.txt" file. If this is missing or not set to none it is not permission to test the hosting resource. This field MUST NOT appear more than once.
- Field { Permission: none }
- Example: none

### **Policy**
- Definition (recommended): This directive allows you to link to where your security policy and/ or disclosure policy is located.  This can help security researchers understand what you are looking for and how to report security vulnerabilities.  If this directive indicates a web URL, then it SHOULD begin with "https://".
- Field { Policy: https://example.com/SECURITY.md }

### **Signature**
- Definition (recommended): This directive allows you to specify a full URI (as per [RFC3986]) of an external signature file that can be used to check the authenticity of a "security.txt" file.  External signature files SHOULD be named "security.txt.sig" and SHOULD be placed under the /.well-known/ path ("/.well-known/security.txt.sig").  If this directive indicates a web URL, then it MUST be begin with "https://".  This field MUST NOT appear more than once.
- Field { Signature: https://example.com/.well-known/security.txt.sig }

## CREDIT
- Development of the companion `security.txt ` draft takes place on Github at: https://github.com/securitytxt/security-txt
- Used this style guide [Bishop Fox - Cybersecurity Style Guide - v1.1](https://www.bishopfox.com/blog/2018/02/hello-world-introducing-the-bishop-fox-cybersecurity-style-guide/)
- [Node.js - SECURITY.md](https://github.com/nodejs/node/blob/master/SECURITY.md)
- [JS Standard Style - SECURITY.md](https://github.com/standard/standard/blob/master/SECURITY.md)
- [electron - SECURITY.md](https://github.com/electron/electron/blob/master/SECURITY.md)
- [tensorflow - SECURITY.md](https://github.com/tensorflow/tensorflow/blob/master/SECURITY.md)

## Contributing
Solo project so far. Code and graphic design contributors are welcome and encouraged to help. Please read [CONTRIBUTING.md](https://github.com/Trewaters/security-README/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to me. 

## Versioning
We use [SemVer](http://semver.org/) for versioning.

**version 1.0.0**
Use Semantic Versioning to help other see at a glance if this document has been updated and what was the scope of the udpate.

- *Major version* incremented when...
  1. Contact information changes in the `SECURITY.md` file or in the `security.txt` file that refers to this file. 
  2. A required field in the `security.txt` has changed in a non backwards compatible manner. 
  3. Updating or changing the Encryption key or protocol.
- *Minor update* is a backward compatible change has been made to the aforementioned files. Usually a field was added or changed to recommended.
- *Patch update* is when a minor typo is fixed but no significant change has been made.

## Authors
- **Tre' Grisby** - _Initial work_ - [@trewaters on github](https://github.com/trewaters)

## License
**CC BY-SA 4.0**
Creative Commons Attribution-ShareAlike 4.0 International
- tl;dr ( https://creativecommons.org/licenses/by-sa/4.0/ )
- legal code ( https://creativecommons.org/licenses/by-sa/4.0/legalcode )

## Acknowledgments
- I tip my hat to [EdOverflow](https://github.com/EdOverflow)! 
- Special thank you to my mom, wife, and daughter! Without their love and support this would gone nowhere.
- Gratitude is the attitude!

#### NOTES
- Source material for this `security.txt` **proposed standard** can be found at: https://tools.ietf.org/html/draft-foudil-securitytxt-04
- Development of the `security.txt ` draft takes place on Github at: https://github.com/securitytxt/security-txt
- A mailing list for `security.txt` is available for discussion at: https://www.freelists.org/list/securitytxt

**Timeline:** 
- This all started on November 1, 2018 when I gave a talk at SFNode titled "Node.js Security best practices". I asked everyone to start using a `SECURITY.md` file in their open source projects. Then I realized such a specification didn't actually exist. So I started one by modifying the current `security.txt` specs, and here we are.
- On November 4th this was committed to the Node.js foundation [see commit here...](https://github.com/nodejs/node/commit/472a3d890bcd1c6799658d72bb813626a16d0adc)