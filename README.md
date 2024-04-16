# Canny Debugging Test

Howdy Candidate, we've created this pared down version of Canny to get a better idea of your experience debugging web applications. Best of luck!

## Getting Started

1. **Initialize your environment**

We recommend using nvm for managing node versions.

Install nvm from [here](https://github.com/creationix/nvm)

Then install the node version for this assessment:

```sh
nvm i
```

1. **Install dependencies**

Next you'll need to install this app

```sh
npm install
```

1. **Run the backend**

The backend is a node server. Everything to do with the server lives in `/server`.

Terminal tab #1:

```sh
npm run backend
```

1. **Run the frontend**

Webpack is used to bundle and serve our app. Everything to do with the frontend lives in `/app`.

Terminal tab #2:

```sh
npm run frontend
```

Once everything is running, you should see the app running http://127.0.0.1:8080.

## Customer Issues

For each of the following issues:

1. Identify the issue
1. Apply the fix
1. Provide a response to each technical customer in 1-2 sentences

**Customer 1:** When I open the application, my posts do not load and all I see is a 'server error'.

- Issue: This due to the missing key "name" in the SSOtoken jwt which was mis-spelled as "nayme" and when decoding the jwt during authentication, the server was looking for the key field "name". Hence the server error.
- Fix: We have updated the SSOToken jwt and the issue was fixed. NOTE: You might have to refresh the page before you actually see the fix.

**Customer 2:** When I click on "Top" or "Old", the selector does not update with my new selection.

- Issue: The 'sort by' component's state was being changed before actually changing the sort by value which came in later.
- Fix: We have fixed the issue, please try again. NOTE: You might have to refresh the page before you actually see the fix.

**Customer 3:** When I sort by "Top", there are posts with only 28 votes ranking higher than posts with 180 votes!

- Issue: The sorting mechanism was not accounting for the descending order when the number of posts in the posts list was 2.
- Fix: We have updated the sorting algorithm to fix this issue, please try again. NOTE: You might have to refresh the page before you actually see the fix.


**Customer 4:** When I page through posts, although the posts are changing, the vote count in the top left corner does not match the total count of votes of the displayed posts.

- Issue: When changing the page number, the vote count may come in before all the posts were brought in due to asynchronous nature of the functions. So awaiting the fetchVotes and then dispatching the recountVotes will make sure that all the votes are in before the total votes are counted.
- Fix: We have fixed the vote counting process, please try again. NOTE: You might have to refresh the page before you actually see the fix.

## 🎉 You're Done 🎉

Congrats on completing our assessment. All that is left for you to do is submit your assessment. We made a command that will zip your submission and send it to us. Send us an email to confirm that we got it.

```sh
npm run submit
```
