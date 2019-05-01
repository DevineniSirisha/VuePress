# Test Cases
- **Test cases:**
If you are new to testing, you may find it hard to discover the benefits of testing. But once you get into the habit of writing tests, your code quality and confidence over code improve drastically.

To build a better mental model, testing is divided into multiple categories, so that you can write different types of test cases with a clear boundary.
- **Test cases:**
Unit tests
Unit tests are written to test small pieces of code in isolation. For example: Testing a service directly, without worrying about how that service is used in real world.

Unit tests ensure that each part of the application works fine on its own and also it is easier to write them since you do not need the whole application to work before you can test it.
- **Test cases:**
Example
```
const { test } = use('Test/Suite')('Example unit test')
const UserValidator = use('App/Services/UserValidator')

test('validate user details', async ({ assert }) => {
  const validation = await UserValidator.validate({
    email: 'wrong email'
  })

  assert.isTrue(validation.fails())
  assert.deepEqual(validation.messages(), [
    {
      field: 'email',
      message: 'Invalid user email address'
    }
  ])
})
- **Functional tests:**
```

Functional tests are written to test your app like an end user. Which means opening up a browser programmatically and visiting the web pages to ensure they all work fine.

```
const { test, trait } = use('Test/Suite')('Example functional test')
trait('Test/Browser')

test('validate user details', async ({ browser }) => {
  const page = await browser.visit('/')

  await page
    .type('email', 'wrong email')
    .submitForm('form')
    .waitForNavigation()

  page.session.assertError('email', 'Invalid user email address')
})
```
Both the above examples validate the email address for a given user, but the approach is different based on the type of test you are writing.
- **Setup**

First, we need to set up the testing engine by installing it from npm.
```
adonis install @adonisjs/vow
```
Next, make sure to register the provider inside aceProviders array, since we do not want to boot testing engine when running your application in production.
```
start/app.js
const aceProviders = [
  '@adonisjs/vow/providers/VowProvider'
]
```
Once @adonisjs/vow is installed, it creates a sample test for you, along with some other files described below.
- **vowfile.js:**

The vowfiles.js is loaded before your tests are executed. You can use this file to define tasks that should occur before and after running all the tests.
- **.env.testing**

This file contains the environment variables to be used when running tests. This file gets merged with .env file so must only define values you want to override from the .env file.

test
All of the application tests are stored inside subfolders of test directory.
- **Running tests**

Vow provider automatically creates a unit test for you, which can be executed by running the following command.
```
adonis test
```

Output
![Images](./testCases.png) 

