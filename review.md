<h3 align="center"><img src="https://github.com/SukeeratSG/dump-public/blob/iron/Assets/havoc_favicon.svg" width="30%" height="30%"></h3>
<h3  align="center">This is a guide for how to use the official review system of Havoc-OS</h3>

###  Code Review System

- We at havoc take authorship and open source very seriously.
- That's why every change passes through  a open source code review
- Url : [review.havoc-os.com](https://review.havoc-os.com)

###  An example

- Add your changes to an existing Havoc-OS Repo
- Sign up and set up your [ssh keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- And then simply push your changes like so

```bash
    
    git push ssh://**username**@review.havoc-os.com:29428/Havoc-OS/android_**XXX** HEAD:refs/for/**version**%topic=**topic**

    For example :

    git push ssh://sukeerat@review.havoc-os.com:29428/Havoc-OS/android_frameowrks_base HEAD:refs/for/eleven%topic=Flashlightoncall

```

- This works for any changes that you want to include in Havoc-OS for any repo.