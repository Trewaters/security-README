# `security.md` - Responsible Security Disclosure README standard

## What should the `security.md` do?
What is the main purpose of `security.md`?

The main purpose of `security.md` is to help make it easier for companies and security researchers when trying to secure platforms. Thanks to `security.md`, security researchers can easily get in touch with companies about security issues.

Below are some recommnedations on what to include in your `security.md`:
- **"Our security policy and Your responsibility"**: This is the place for the security policy you wish uphold. This is also the place to put the "tl;dr" version of your Security Disclosure requirements.
- **"MY-PROJECT Checklist: Security Recommendations"**: This is where you outline best security practices when using "MY-PROJECT". This helps someone use the project better and avoid common security mistakes.

## Our security policy and Your responsibility
- **POLICY**:

*Our security policy is to avoid leaving the ecosystem worse than we found it. Meaning we are not planning to introduce vulnerabilities into the ecosystem.*

- **SECURITY DISCLOSURE**:

*Your responsibility is to report vulnerabilities to us using the guidelines outlined below.*

Discuss in tl;dr ( or ELI5 ) how someone could/should disclose a vulnerability to "MY-PROJECT". Then expand on this with "How To Disclose a vulnerability in detail". Please give detailed steps on how to disclose the vulnerability. Keep these OWASP guidelines in mind ( https://www.owasp.org/index.php/Vulnerability_Disclosure_Cheat_Sheet ) when creating your disclosure policy. Below are some recommendations for security disclosures:
- "MY-PROJECT" security contacts { contact: mailto:trewaters@hotmail.com }
- Communication expectations: How much time it could take "MY-PROJECT" to respond? What type of response to expect?
- Disclosure format: When disclosing vulnerabilities please 
  1. include scope of vulnerability, 
  2. document steps to identify and 
  3. how to exploit vulnerability

## "MY-PROJECT" Checklist: Security Recommendations
Follow these steps to improve security when using "MY-PROJECT".
1. ...SEE SOMETHING
2. ...SAY SOMETHING

### 1)...SEE SOMETHING
We suggest you goto #2 if this happens.

**Why?**
Through experience we have found it is best to goto #2 in this situation.

**How?**
Read our suggestions on [Reporting Security Issues](https://github.com/Trewaters/security-README/blob/master/security.md#our-security-policy-and-your-responsibility).
`SHOW HOW TO CODE EXAMPLES IF POSSIBLE`
or goto #2

## Version
**version 0.0.1**

Use Semantic Versioning to help other see at a glance if this document has been updated and what was the scope of the udpate.

- Major version incremented when contact information changes in the `security.md` file or in the `security.txt` file that refers to this file. Or a required field in the `security.txt` has changed in a non backwards compatible manner.
- Minor update is a backward compatible change has been made to the aforementioned files.
- Patch update is when a minor typo is fixed but no significant change has been made.

## Getting Started
- Create a `security.txt` file. See example below:
```
  # Our security address
  Contact: mailto:security@example.com
  
  # Our PGP key
  Encryption: https://example.com/pgp-key.txt
  
  # Our security policy
  Policy: https://example.com/security.md
  
  # Our security acknowledgments page
  Acknowledgments: https://example.com/hall-of-fame.html
  
  # Verify this security.txt file
  Signature: https://example.com/.well-known/security.txt.sig
```

- Create a `security.md` file. see example below:
```
## Our security policy and Your responsibility
## "MY-PROJECT" Checklist: Security Recommendations
## Version

```

### `security.txt` Fields
#### **Acknowledgments**
- Definition: This directive allows you to link to a page where security researchers are recognized for their reports.  The page being linked to SHOULD list individuals or companies that disclosed security vulnerabilities and worked with you to remediate the issue.
- Field { Acknowledgments: https://example.com/hall-of-fame.html }
- Example security acknowledgment webpage:
 > We would like to thank the following researchers:

 > (2017-04-15) Frank Denis - Reflected cross-site scripting
 > (2017-01-02) Alice Quinn  - SQL injection
 > (2016-12-24) John Buchner - Stored cross-site scripting
 > (2016-06-10) Anna Richmond - A server configuration issue

#### **Contact**
- Definition (required): This directive allows you to provide an address that researchers SHOULD use for reporting security issues.  The value MAY be an email address, a phone number and/or a contact page with more information. If this directive indicates a web URL, then it MUST be begin with "https://". The value MUST follow the general syntax described in [RFC3986]. This means that "mailto" and "tel" URI schemes MUST be used when specifying email addresses and telephone numbers. The precedence SHOULD be in listed order.  The first field is the preferred method of contact.
- Field { contact: mailto:trewaters@hotmail.com }
- Example:
> Contact: mailto:security@example.com
> Contact: tel:+1-201-555-0123
> Contact: https://example.com/security-contact.html

#### **Encryption**
- Definition (recommended): This directive allows you to point to an encryption key that security researchers SHOULD use for encrypted communication.  You MUST NOT directly add your key to the field, instead the value of this field MUST be a URI pointing to a location where the key can be retrieved from.  If this directive indicates a web URL, then it MUST be begin with "https://". When it comes to verifying the authenticity of the key, it is always the security researcher's responsibility to make sure the key being specified is indeed one they trust.  Researchers MUST NOT assume that this key is used to generate the signature file
- Field { Encryption: https://example.com/pgp-key.txt }
- Example of a PGP key available from an OPENPGPKEY DNS:
> Encryption: dns:5d2d37ab76d47d36._openpgpkey.example.com?type=OPENPGPKEY
- Example of a PGP key being referenced by its fingerprint:
> Encryption: openpgp4fpr:5f2de5521c63a801ab59ccb603d49de44b29100f

#### **Hiring**
- Definition (recommended): The "Hiring" directive is used for linking to the vendor's security-related job positions.  If this directive indicates a web URL, then it SHOULD be begin with "https://".
- Field { Hiring: https://example.com/jobs.html }
- Example: none

#### **Permission**
- Definition (required): The presence of the "Permission" directive is used to indicate to security researchers that they MUST NOT perform any kind of testing against the resource hosting the "security.txt" file. If this is missing or not set to none it is not permission to test the hosting resource. This field MUST NOT appear more than once.
- Field { Permission: none }
- Example: none

#### **Policy**
- Definition (recommended): This directive allows you to link to where your security policy and/ or disclosure policy is located.  This can help security researchers understand what you are looking for and how to report security vulnerabilities.  If this directive indicates a web URL, then it SHOULD begin with "https://".
- Field { Policy: https://example.com/security.md }
- Example:

#### **Signature**
- Definition (recommended): This directive allows you to specify a full URI (as per [RFC3986]) of an external signature file that can be used to check the authenticity of a "security.txt" file.  External signature files SHOULD be named "security.txt.sig" and SHOULD be placed under the /.well-known/ path ("/.well-known/security.txt.sig").  If this directive indicates a web URL, then it MUST be begin with "https://".  This field MUST NOT appear more than once.
- Field { Signature: https://example.com/.well-known/security.txt.sig }
- Example:

### NOTES
- Source material for this `security.txt` **proposed standard** can be found at: https://tools.ietf.org/html/draft-foudil-securitytxt-04
- Development of the `security.txt ` draft takes place on Github at: https://github.com/securitytxt/security-txt
- A mailing list for `security.txt` is available for discussion at: https://www.freelists.org/list/securitytxt

### License
**CC BY-SA 4.0**
Creative Commons Attribution-ShareAlike 4.0 International
- tl;dr ( https://creativecommons.org/licenses/by-sa/4.0/ )
- legal code ( https://creativecommons.org/licenses/by-sa/4.0/legalcode )
