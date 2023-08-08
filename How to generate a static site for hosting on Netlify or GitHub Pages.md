Creating a static site to host on Netlify or GitHub Pages is a straightforward process. Static sites are easy to manage and require minimal resources. Here's how you can generate one:

1. **Choose your static site generator**: There are many static site generators available, such as [[Jekyll]], [[Hugo]], Eleventy, Gatsby etc. Choose the one that best fits your needs.

2. **Install the generator**: For example, if you choose Jekyll, you will need Ruby installed on your machine. Once Ruby is installed, you can install Jekyll by running `gem install jekyll bundler` in your terminal.

3. **Create a new project**: Use the generator's command to create a new project. For Jekyll, this would be `jekyll new my-awesome-site`.

4. **Build the site**: Run the build command for your generator (e.g., `jekyll build`) to generate the HTML files for your site.

5. **Customize your site**: Change the theme, add content to your pages, and modify anything else you want for your website.

6. **Test locally**: Before uploading it to Netlify or GitHub Pages, test it locally using commands like `jekyll serve`. 

7. **Push to GitHub or Deploy on Netlify**:

   - *GitHub Pages*: Create a repository on GitHub and push your website files there (make sure to push them into a branch named `gh-pages` if it's a project repository or into `master` if it's a user/organization repository). Then go to settings of repo and under GitHub Pages section select branch which contains web page files.
   
   - *Netlify*: Sign up for Netlify and follow their instructions for drag-and-drop deployment or continuous deployment from Git.

8. **Configure custom domain (optional)**: You can also configure custom domain names with both Netlify and Github pages by adding CNAME file with domain name in source code and configuring DNS settings with domain provider.

That's it! Now you have a live static site hosted on either Netlify or GitHub Pages.

Remember that while creating content for these sites may involve writing in Markdown language or HTML/CSS/JavaScript depending on how complex your website would be and which static site generator you have chosen.
   
Static websites are great because they're fast, secure, cheap (or even free), easy to deploy and maintain due its simplicity but they might not be suitable for every use case since they lack server-side processing which could make them less dynamic compared with CMS like Wordpress etc unless combined with other tools like headless CMS or serverless functions etc which do require little bit more setup involved compared with traditional CMS solutions but could provide best of both worlds i.e speed of static sites + dynamic capabilities if needed.
