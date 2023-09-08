+++
author = "Elise Morgan"
title = "How-To: Build a Simple Website with Hugo and GitHub Pages"
date = "2023-09-07"
description = "How I Built This Site"
ShowToc = true
+++

---
#### By Someone Who Didn't Know What They Were Doing When They Started

---

Welcome to my website! I built this website using Hugo and I host it on GitHub Pages.

I started this process with a URL and no clue what I was doing. This guide is for anyone who wants to create a simple website to showcase work but doesn't know where to begin.

I hope that someone else with no technical experience can follow these steps to build their website and skip all the frustrating hours I spent figuring this out on my own. This may not be the process that makes the most sense to a tech pro, but I know it works.

> I did all of this on a Mac. If you are using a different operating system, your exact steps may vary.

---

## Building Your Site
### 1. Open Terminal
   
   Search for Terminal:

   ![screenshot showing opening Terminal application on Mac](/images/terminalSearch.png)

   Terminal Window:
   
   ![screenshot of open Termincal](/images/macTerminal.png)

### 2. Install Hugo
[Follow Hugo installation instructions.](https://gohugo.io/installation/)

### 3. Install Git
**1. Check that Git is installed on your computer:**
        
        git --version
If Git is installed, you will see a message displaying your current version:

![Screenshot of Git version on my computer](/images/gitVersion.png)
    
**2. If Git is not installed, an installation may automatically start.** 

If not, [follow the Git installation instructions.](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### 3. Choose Your Theme
    
**1. Choose the look of your site from Hugo's [catalogue of themes](https://themes.gohugo.io).**

I used [PaperMod](https://themes.gohugo.io/themes/hugo-papermod/) on this site.

**2. Click Download to go to your theme's GitHub page.**

Keep this GitHub page open for later.

### 4. Build Your Local Repository
    >>This is a Terminal command<<
> `[]`inside`command`snippets show where you will insert your unique value. Paste these lines into your terminal, but eliminate the`[]`after inserting your unique value.
   
**1. Build hugo site:**
   
        hugo new site [name of directory]
Use something short for your directory name. I used portfolio.
   
**2. Navigate to new site directory:**
   
        cd [name of folder]
> Moving forward, you must be in your directory to do anything. If you see:
![screenshot showing hugo error that says: Error: command error: Unable to locate config file or config directory. Perhaps you need to create a new site. Run `hugo help new` for details.](/images/hugoNoDirectoryError.png) 
>That means you are not in your site's directory folder. Use the `cd` command to navigate to your directory.

### 5. Add Your Theme
   **1. Initialize Git:**
   
        git init
   
   **2. Use Git to import your chosen theme into your site's repository:** 
   
        git submodule add [the directory for your theme]
Find the directory for your theme in the theme's GitHub ReadMe file. There will be a `themes/[theme name]` after the url. Don't leave that out!
   
   **3. Add the theme to your site's configuration file:**
    
        echo "theme = '[theme name]'" >> hugo.toml
   **4. Each theme is unique and may require alternative or additional steps.**

### 6. [Download Visual Code Studio](https://code.visualstudio.com/download)
This is the interface that I use to navigate my site directory and create content.

### 7. Set Up Your Site
>This is where I struggled as someone who had no understanding of how these sites work. My breakthrough moment came when I realized that my theme included an example site with all its own files. This meant, I could mimic the example site files to successfully build my own. I recommend you do the same!
   
   **1. Open site directory in Visual Code Studio:**
   
   ![Screenshot of action](/images/openVSCodeFile.png)

   You can now see and you entire site directory in VS Code:

   ![Screenshot of File directory in VS Code](/images/VSCodeFileMap.png)

   **2. Look through the example site files included in your theme Portfolio > themes > [theme name] > example-site:**
    
![Screenshot of directory of theme's example site](/images/exampleSiteDirectory.png)

   **3. Set Up Your Config File:**
    
*hugo.toml* was created when you set up the Hugo site. This file defines basics, like language. It is where you create site headers and navigation menus.

Add additional elements to your *hugo.toml*, such as headers, by following your example site's *.toml* file.


### 8. Create Homepage Content
In Visual Code Studio:

**Follow your theme's example site to determine how to setup your homepage content.**

Depending on your theme, you may need to create a file in your *content* folder titled _index.md to display content on your homepage. For other themes, the homepage content will be included on in the config file.


### 9. Create New Content Pages
In Visual Code Studio:

   **1. Create a New Folder in the *content* folder within your directory. Name the folder how you want the heading to appear on your site:**
   
![Screenhot of new folder in content folder](/images/newContentFolder.png)

   **2. Create New File in the new *[Projects]* folder to create a post.**

   **3. In your new Post, enter the following information at the top:**
   
`+++`

`author = "[Your Name]"`

`title = "[Post Title]"`

`date = "[The date of posting]"`

`description = "[Description of the post]"`

`+++`

   **4. Below the final `+++`, enter the content of your post.**

You will use Markdown to write all content on Hugo. Writing Markdown is similar to writing a text document, but it requires simple manual formatting. [Follow this Markdown guide.](https://www.markdownguide.org/cheat-sheet/)
   
   **5. Save the new file and close.**

### 10. Launch Hugo
**1. In the Terminal, enter the command:** 
    
        hugo server

> Troubleshooting: If Hugo says it cannot launch, be sure you navigated into your site directory with `cd [directory name]` before launching Hugo.    

Hugo is now building your site on your local server. Run http://localhost:1313/ on your browser to see your site.

You can continue to create and edit your site files, and preview your updated site on your local server. Hugo updates saved changes in real time.

---

## Publishing Your Site Online

### 1. Push Site to GitHub
Follow these steps to host your site on GitHub Pages.

   **1. If you don't already have one - [sign up for a GitHub account.](https://github.com)**

   **2. For Mac Users:**
1. Create a file in your directory named ".gitignore"
   
2. Type `*/.DS_Store` in the file content.
3. Save file and close.

**3. Create GitHub custom workflow:**
1. Create a file in your directory named ".github/workflows/hugo.yaml"
   
2. Copy and paste the YAML provided [here, in Step 6](https://gohugo.io/hosting-and-deployment/hosting-on-github/) into the new file.
3. Save file and close.
   
**4. Create a New Repository (repo) in GitHub:**
   
   ![Screenshot of action](/images/newRepo.png)

**5. GitHub gives you the unique command lines you will need to push your site to GitHub:**
   
   ![Screenshot of provided GitHub command lines](/images/gitHubCodePage.png)

**6. Navigate to your site directory:**

        cd [portfolio]
**7.  Initialize Git in your directory:**
   
        git init
**8.  Add all files to Git index:**
        
        git add -A
**9.  Commit added files with a message:**
        
        git commit -m 'Added all site files'
**10. Add your GitHub repo as your new remote origin:**
        
        git remote add origin [The Repo URL from GitHub]
   ![Screenshot of GitHub command lines](/images/gitHubCode.png)

**11. Tell GitHub to push to your repo's Main branch:**
        
        git branch -M main
**12. Push to GitHub:**
        
        git push -u origin main
The -u command defines the remote origin (aka your GitHub server) to always be the "upstream" reference. Now, when you push future changes, they automatically go to your site repo.

**13.   Enter you GitHub username and password when prompted by Terminal:** 
    
>Two things to be aware of:
> * If you have two-factor authentication turned on for your GitHub account, your password will be invalid. See Step 14 below.
> * For security, the Terminal will not display what you enter for your password. So, it looks like your typing is not inputting. The password is there but it is hidden. Type or paste your password and press Enter.

**14.   Create GitHub token to get around two-factor authentication block:**
        
1. Go to your GitHub Settings:
   
![Screenshot of navigation to GitHub Settings](/images/gitHubSettingsNav.png)
  
2.  Click Developer Settings:
   
![Screenshot of Dev Settings nav](/images/devSettingsNav.png)
        
3. Click Tokens (classic) in the Personal access tokens drop-down:
   
![Screenshot of Tokens nav](/images/tokensNav.png)

4. Click Generate new token (classic):
   
![Screenshot creating new token](/images/newToken.png)

5. Immediately paste the token into the "Password" field when prompted by the Terminal.

### 2. Deploy Site on GitHub Pages

   **1.  Go to your repo on GitHub. It will be populated by all files from your site directory.**
   
   **2.  In the repo's menu, click Settings, then click Pages:**

![Screenshot of step](/images/navPageSettings.png)

   **3.  Set source to GitHub Actions:**

![Screenshot of action](/images/gitHubActions.png)

   **4.  In the repo's menu, click Actions:**

![Screenshot of action](/images/pageActions.png)

You will see an action being deployed, it will likely still be in progress and be yellow. When the deployment is complete, the icon will change to green with a check mark.

   **5.  Go back to your repo's Settings > Pages. Click your site's GitHub generated URL to see your site online.**


### 3. Purchase Your Custom URL
   **1. [Read GitHub's Custom Domain Recommendations.](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)**

   **2. To find out if a URL (domain) is available, type your desired URL into a browser:**
        
If it is available, you will see a message like this:

![Screenshot of available URL page](/images/availableURL.png)

Do not search this URL again until you have purchased it. Repeatedly searching for the URL will raise the price.

   **3. Purchase your custom URL. There are many places you can do this. Here is a short list:**

* [Google Domains](https://domains.google)
* [Squarespace](https://www.squarespace.com/domain-name-search)
* [GoDaddy](https://www.godaddy.com/domains)
* [Pair Domain](https://www.pairdomains.com)

> I purchased my domain from Pair Domain. Therefore, my instructions for connecting your URL to your site will be shown on Pair Domain.

### 4. Add SSL Security Certificate to Domain
The SSL ceritifcate will give your URL the https:// in the beginning. If your domain does not have an SSL certificate, visitors will be warned that your site is not secure.

   **1. Go to your SSL management within your domain manager.**

   **2. Select SSL certitificate and proceed with the domain manager's instructions:**
   
   ![Screenshot of action](/images/sslCertificate.png)

### 5. Add Custom DNS Records to Domain
   **1. Enable Custom DNS Records for your domain.**

   **2. Add the following A records exactly:**
   
* `185.199.108.153`

* `185.199.109.153`

* `185.199.110.153`

* `185.199.111.153`    

**3. Enter your GitHub Page URL in the CNAME destination.**

   Your DNS records will look like this:
   
   ![Screenshot of complete DNS records](/images/urlDestinations.png)

### 6. Enter your custom domain on GitHub Pages
Enter your custom domain in your GitHub Page settings:

![Screenshot of action](/images/customDomain.png)

---

## Now Visit Your New Site! 🎉🎉
