# Slides

## Building tex abstract with:

### (a) Github Actions
#### Setting it up
1. Add `shh-rsa` key in https://github.com/settings/keys following [the documentation](https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) in github.

2. Create a new secret variable called `DEPLOY_KEY` in 
https://github.com/mxochicale/itds2020/settings/secrets 

Where the value is taken from `id_rsa` with 
`vim ~/.ssh/id_rsa` which looks like:  
```
-----BEGIN RSA PRIVATE KEY-----
...
-----END RSA PRIVATE KEY-----
```

3. Create a generated-pdfs branch for the pdf files [(see more)](https://www.freecodecamp.org/forum/t/push-a-new-local-branch-to-a-remote-git-repository-and-track-it-too/13222).
```
git checkout -b generated-pdfs
rm -rf * README.md .github .gitignore *swp ~.git 
git add -A
git commit -m 'clean generated-pdfs branch'
git push origin generated-pdfs
```

4. Create branch for drafting document
```
git checkout master
git checkout -b 01-drafting-slides


5. add latex document path

6. Create github action workflow
* Create main.yml 
```
mkdir -p .github/workflows
cd .github/workflows && wget https://raw.githubusercontent.com/mxochicale/learning-latex-action/master/.github/workflows/main.yml
```
* Setting up variables for pdf documents and keys in .github/workflows/main.yml. 
See this [main.yml](https://github.com/mxochicale/learning-latex-action/blob/master/.github/workflows/main.yml) as example.


7. commit changes
```
git add -A
git commit -m 'genesis of slides'
git push origin generated-pdfs
```



### (b) Local build
#### build LaTeX projet
```
make
```
#### clean LaTeX project
```
make clean
```
