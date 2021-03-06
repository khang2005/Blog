---
layout: drafts
title: sample1
date: 2021-01-30 15:23:19
tags: [ Javascript ]
---

# Overview


A Promise is either in an unresolved or resolved state. We create using
new Promise, and initially, it is in the unresolved state. 
The Promise object transitions to the resolved, where either its resolve or reject functions are called. 


{% codeblock %}

Promise objects can be in one of three states:
Pending: This is the initial state, which is neither fulfilled nor rejected.
Fulfilled: This is the final state, where it executes successfully and produces a result.
Rejected: This is the final state, where execution fails.

{% endcodeblock %}

We generate a Promise in the following way:

{% codeblock %}
function asyncFunction(arg1, arg2) {
  return new Promise((resolve, reject) => {
    //perform some task or computation that's asynchronous
    // for any error detected:
    if (errorDetected) return reject(dataAboutError);
    // When the task is finished
    resolve(theResult);
  });
};

/* This is the pattern that we use when promisfying an asynchronous function
that use callbacks */

function readFile(filename) {
  return new Promise((resolve, reject) => {
    fs.readFile(filename, (err, data) => {
    if (err) reject(err);
    else resolve(data);
    });
  });
};

asyncFunction(ar1, arg2)
.then(result) => {
  // the operation succeeded
  // do somethgin with the result 
  return newResult;
})
.catch(err => {
  //an error occurred
});
{% endcodeblock %}
