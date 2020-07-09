# random.dog

[![Build Status](https://travis-ci.org/AdenFlorian/random.dog.svg?branch=master)](https://travis-ci.org/AdenFlorian/random.dog)

The nodejs code behind [random.dog](https://random.dog)

## Prerequisites

- `node@^10.1.0`
- `yarn@^1.6.0`

## Setup

- `git clone`
- `yarn`
- `yarn start`
- <http://localhost:8080/>

## Tests

- `yarn test`
- `yarn tdd`

## Security Setup

- `/review` requires a cookie named `bone`
  - The value should be some base64 encoded text that, when hashed with bcrypt, matches the hash stored in a file named `secret.json` located in the project root folder
  - The json in `secret.json` should be like this:
    -  `{"secret": "<put hash here>"}`
  - Use [bcrypt-cli](https://www.npmjs.com/package/bcrypt-cli) to hash the password to store in the `secret.json`
  - Example cookie header:
    - `Cookie: bone=cGFzc3dvcmQ=`

## API

On the `GET /woof`, `GET /woof.json`, and `GET /doggos` endpoints, you may add a query parameter called `filter` which should have 1 or more file extensions, separated by commas. When hitting any of the above 3 endpoints with the `filter` param, that endpoint will only return dogs that do not have one of the filtered extensions. There is also an `include` query param that does the opposite of `filter`.

Example: `GET random.dog/woof?filter=mp4,webm` will only return dogs that do not have an extension of `mp4` or `webm`.

Example: `GET random.dog/woof?include=mp4,webm` will only return dogs that do have an extension of `mp4` or `webm`.

## Thanks

This is the fork of an api that i used in [random-dog](https://github.com/LeoMehraban/random-dog) and [DogApp](https://gitub.com/LeoMehraban/DogApp).

so thanks for creating this. i will use it in my next dog related web app. also i don't know why i forked this repo.

also, check to origanal out: [https://github.com/AdenFlorian/random.dog](https://github.com/AdenFlorian/random.dog)
