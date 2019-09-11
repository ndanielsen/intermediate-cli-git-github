
# Git Intermediate - Remotes and Conflicts 

In the previous section, we looked at git branches and merging them together.

Now we will look at git remotes and handling merge conflicts.

At this point, you should have forked and cloned to your local machine the github respository [Nicecream Icecream - Los Angeles's Finest Hipster Icecream Startup](https://github.com/ndanielsen/nicecream.github.io)


#### What is a remote respository in git?

Type in your terminal: 

`git remote`

Let's use the commandline to learn a little more about `git remote`

`git remote --verbose`


The git remote command lets you create, view, and delete connections to other repositories. Remote connections are more like bookmarks rather than direct links into other repositories. Instead of providing real-time access to another repository, they serve as convenient names that can be used to reference a not-so-convenient URL.


Add and remove a `remote` like this:

```
git remote add {nickname} {url}

git remote remove {nickname}


```

Protip: It is incredibly helpful to pick a meaningful name for the remote such as the owner of the repository or a nickname that is easy to type.


### Exercise

Add the main repository as a `remote` named `ndanielsen`

You can find the repo information [here](https://github.com/ndanielsen/nicecream.github.io)

**Hint:** checkout the "clone or download" button to get the url

#### Team Development Flow Using Branches

So far we've been crushing it as the solo developer for the coolest icecream startup in Los Angeles.

We're doing so well that we've been able to add another developer to the team.

Just like in real life when there are multiple people working on the same tasty topics, there is bound to be conflict. Not all conflict is bad, it just means we need to resolve it quickly to keep the work moving forward.

As the `master` represents what is in publically available in `production`, we will need to have another branch for building out our next release.

We will be calling this the `develop` branch.


### Create A Develop branch

Let's create a new development branch off of master.

```
git checkout master

git branch -b develop

```

### Merging in the existing develop branch

Let's make sure that we're building off of the latest work. We need to add the `remote` repository of the main repository if we haven't already.


```
git remote add ndanielsen {url}

git fetch --all

git merge ndanielsen/develop

```

Oops... looks like we have a merge conflict. We need to be resolve it.

Checkout your `index.html` to see what it looks like in the html.


### Merge Conflicts

To resolve, delete the conflict markers <<<<<<<, =======, >>>>>>> and make the changes you want in the final merge.


Here's what a merge conflict typically looks like. Typically, there is overlapping work that `git` has decided a human needs to figure out what the right answer is.


```

If you have questions, please
<<<<<<< HEAD
raise your hand
=======
ask your question to a TA.
>>>>>>> branch-a

```

**Warning:** Git will allow you to merge conflicted code.

'
### Exercise

Resolve the conflicts from the merge.
Ask any questions that you have.

Please fill out the post-workshop survey: [https://tinyurl.com/la-tech-workshop](https://tinyurl.com/la-tech-workshop)




### Resources

- [Resolving a merge conflict using the command line](https://help.github.com/en/articles/resolving-a-merge-conflict-using-the-command-line)
- [git syncing](https://www.atlassian.com/git/tutorials/syncing)