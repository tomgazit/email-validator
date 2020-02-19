# email-validator
A simple module to validate an email address.

The validator supports quoted-string for the "local" part of the email address (as stated in RFC3696).

* dot ., provided that it is not the first or last character unless quoted, and provided also that it does not appear consecutively unless quoted (e.g. John..Doe@example.com is not allowed but "John..Doe"@example.com is allowed)

* space and special characters "(),:;<>@[\] are allowed with restrictions (they are only allowed inside a quoted string, as described in the paragraph below, and in addition, a backslash or double-quote must be preceded by a backslash);

## Installation
Install via NPM:

```bash
npm install email-validator-qs

```

## Usage

#### javascript

```javascript

var validator = require("email-validator-qs");

validator.validate('test@email.com'); // true
validator.validate('another.test@email.com'); // true
validator.validate('another..test@email.com'); // false
validator.validate('"another..test"@email.com'); // true
validator.validate('"anot\her..test"@email.com'); // false
validator.validate('"anot\\her..test"@email.com'); // true
validator.validate('"anot"her..test"@email.com'); // false
validator.validate('"anot\"her..test"@email.com'); // true

```

#### TypeScript

```typescript

import * as EmailValidator from 'email-validator-qs';

EmailValidator.validate('test@email.com'); // true
EmailValidator.validate('another.test@email.com'); // true
EmailValidator.validate('another..test@email.com'); // false
EmailValidator.validate('"another..test"@email.com'); // true
EmailValidator.validate('"anot\her..test"@email.com'); // false
EmailValidator.validate('"anot\\her..test"@email.com'); // true
EmailValidator.validate('"anot"her..test"@email.com'); // false
EmailValidator.validate('"anot\"her..test"@email.com'); // true

```

## Contribute

Contributions welcome! Check the ``LICENSE`` file for more info.

## Meta

This library was originally forked from:
https://github.com/manishsaraan/email-validator by Manish Saraan
**Thank you!**

Distributed under the unlicense public domain. See ``LICENSE`` for more information.

[https://github.com/tomgazit/email-validator-qs](https://github.com/tomgazit/email-validator-qs)
