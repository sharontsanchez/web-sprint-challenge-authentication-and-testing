# Authentication and Testing Sprint Challenge

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This challenge allows you to practice the concepts and techniques learned over the past sprint and apply them in a concrete project. This sprint explored **Authentication and Testing**. During this sprint, you studied **authentication, JSON web tokens, unit testing, and backend testing**. In your challenge this week, you will demonstrate your mastery of these skills by creating **a dad jokes app**.

This is an individual assessment. All work must be your own. All projects will be submitted to Codegrade for automated review. You will also be given feedback by code reviewers on Monday following the challenge submission. For more information on the review process [click here.](https://www.notion.so/bloomtech/How-to-View-Feedback-in-CodeGrade-c5147cee220c4044a25de28bcb6bb54a)

You are not allowed to collaborate during the sprint challenge.

## Project Setup

- [x] Run `npm install` to install your dependencies.
- [x] Build your database executing `npm run migrate`.
- [x] Run tests locally executing `npm test`.

## Project Instructions

Dad jokes are all the rage these days! In this challenge, you will build a real wise-guy application.

Users must be able to call the `[POST] /api/auth/register` endpoint to create a new account, and the `[POST] /api/auth/login` endpoint to get a token.

We also need to make sure nobody without the token can call `[GET] /api/jokes` and gain access to our dad jokes.

We will hash the user's password using `bcryptjs`, and use JSON Web Tokens and the `jsonwebtoken` library.

### MVP

Your finished project must include all of the following requirements (further instructions are found inside each file):

- [ ] An authentication workflow with functionality for account creation and login, implemented inside `api/auth/auth-router.js`.
- [ ] Middleware used to restrict access to resources from non-authenticated requests, implemented inside `api/middleware/restricted.js`.
- [ ] A minimum of 2 tests per API endpoint, written inside `api/server.test.js`.

**IMPORTANT Notes:**

- Do not exceed 2^8 rounds of hashing with `bcryptjs`.
- If you use environment variables make sure to provide fallbacks in the code (e.g. `process.env.SECRET || "shh"`).
- You are welcome to create additional files but **do not move or rename existing files** or folders.
- Do not alter your `package.json` file except to install extra libraries. Do not update existing packages.
- The database already has the `users` table, but if you run into issues, the migration is available.
- In your solution, it is essential that you follow best practices and produce clean and professional results.
- Schedule time to review, refine, and assess your work and perform basic professional polishing.

## Submission format

- [ ] Submit via Codegrade by pushing commits to your `main` branch on Github.
- [ ] Check Codegrade before the deadline to compare its results against your local tests.
- [ ] Check Codegrade on the days following the Sprint Challenge for reviewer feedback.
- [ ] New commits will be evaluated by Codegrade if pushed _before_ the sprint challenge deadline.

## Interview Questions

Be prepared to demonstrate your understanding of this week's concepts by answering questions on the following topics.

1. Differences between using _sessions_ or _JSON Web Tokens_ for authentication.
The Session and Token-based Authentication methods are used to make a server trust any request sent by an authenticated user over the internet. The main difference is session-based authentication of the connection stores the authentication details. The session method makes the server store most of the details, while in the case of the token-based one the client stores them.

2. What does `bcryptjs` do to help us store passwords in a secure manner?
The bcrypt hashing function allows us to build a password security platform that scales with computation power and always hashes every password with a salt. Hashing user passwords is essential as user data is very crucial for any organization. 

3. How are unit tests different from integration and end-to-end testing?
Integration testing starts at the very early stages of development. Bugs are caught earlier, rather than later, in the cycle. It's easy to integrate with daily builds and easy to test in the development environment. Tests run faster compared to end-to-end tests. Aims to test how external systems work with internal modules, one by one.  Used to test a single process from third-party software that will be used in conjunction with your software.
End-to-end testing is done when the product is almost ready for release. It may be impossible to perform until the product is nearing completion. Tests run slower compared to integration testing. Aims to test the user experience from start to finish. Can be used for either a single process being executed from start to finish or various different processes involving different applications.

4. How does _Test Driven Development_ change the way we write applications and tests?
A key benefit of test-driven development is that it makes the developer focus on requirements before writing code. The TDD method is a more balanced approach for software development which is mostly related to the three main activities: coding, testing, and designing.  Instead of chasing an optimal solution, the code and the test for that code are built for one use case at a time.  Overall, it can streamline the software development process and make it more efficient by delivering feedback faster and encouraging developers to write solid, clean code. 