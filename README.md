# Step-by-Step Guide to Hosting Your Resume with Pelican and GitHub Pages

## Introduction

This README provides a step-by-step guide on how to format and host a resume using Pelican, a static site generator, and publish it using GitHub Pages. The approach follows the principles from Andrew Etter’s *Modern Technical Writing*, which emphasizes static sites, lightweight markup, and version control. 

Creating an online resume with minimal setup is a great way to showcase your work while learning technical writing. By hosting your resume on GitHub Pages, you benefit from the platform’s version control and its simplicity. This guide is designed for anyone with basic Markdown experience who wants a simple way to host their resume online without getting into complex web development. It’s also perfect for people like Marvin McLaren, a finance manager who is diving into technical writing. If you're a beginner with tools like Git, static site generators, or deployment but know the basics of Markdown, this guide will walk you through everything you need to know!

## Prerequisites

Before you begin, make sure you have the following installed:

- **Git** – [Download here](https://git-scm.com/) (Version control is essential for tracking changes. You will use Git to clone repositories, push your changes, and collaborate in the future.)
- **Python** – [Download here](https://www.python.org/downloads/) (Python will run Pelican, the static site generator, to convert your content into HTML.)
- **Pelican** – Install using:
  ```bash
  pip install pelican
  ```
  (Pelican is a static site generator that simplifies the management of content and makes it easy to create clean, maintainable websites from text files.)
- **ghp-import** – Required for deployment:
  ```bash
  pip install ghp-import
  ```
  (This tool automates the deployment of your site to GitHub Pages, making it easier to update and manage.)
- **GitHub account** – [Sign up here](https://github.com/) (GitHub Pages will be used for hosting, providing you with free and simple hosting for your resume.)
- **A text editor that supports Markdown** (VS Code, Atom, or Notepad++) (Markdown editors allow you to create content easily and maintain proper formatting.)

Having these tools in place ensures you have everything needed to start creating and hosting your resume. As you get familiar with Markdown, Pelican, and GitHub Pages, you’ll be able to tweak and maintain your resume more efficiently over time.

---

## Step-by-Step Instructions

### 1. Create a GitHub Repository

**Why GitHub?**  
GitHub is a widely-used platform for hosting static sites. By using GitHub Pages, you benefit from free hosting, version control, and the ability to collaborate on projects with others. GitHub Pages simplifies the process of sharing your resume with potential employers, and it integrates directly with Git to track changes.

1. Log in to GitHub and create a new repository called whatever you want, for this examples call it `website-example`.
   - Make sure to name the repository something simple and clear, like `website-example`, which reflects the project’s content.
2. Ensure the repository is **public** (GitHub Pages requires public repos for free hosting).
3. Clone the repository to your local machine by running:
   ```bash
   git clone https://github.com/your-username/website-example.git
   cd website-example
   ```

Now, you have a local copy of your GitHub repository. Git tracks the history of all changes you make to your resume in this repository, which makes it easy to keep everything organized and maintainable.

### 2. Set Up Pelican

**Why Pelican?**  
Pelican is a static site generator. It’s lightweight and fast, designed to create HTML websites from content written in Markdown or reStructuredText. Using Pelican ensures that your website remains clean and easy to maintain. It also aligns with the principles of modern technical writing, emphasizing simplicity and easy collaboration. Pelican generates static HTML files, which means your resume will load quickly and doesn’t require server-side code to run.

1. Install Pelican if you haven’t already:
   ```bash
   pip install pelican
   ```
2. Run the quickstart setup to create the project’s directory structure:
   ```bash
   pelican-quickstart
   ```
   When prompted, provide the following:
   - **Project directory?** Press Enter (use the current directory)
   - **Website title?** "My Sample Website"
   - **Author name?** Enter your name
   - **What will be the default language of this web site?** [English] Press Enter
   - **Do you want to specify a URL prefix?** e.g., https://example.com  (Y/N)-Y
   - **Do you want to upload your website using GitHub Pages?** (Y/N)-Y
   - **Absolute URL prefix?** `https://your-username.github.io/website-example`
   - **Generate Makefile?** Yes
   - **Use a simple HTTP server?** Yes

Pelican will generate a basic project structure for you.You should get a message like "Done. Your new project is available at C:\..." It’s a good practice to maintain the default structure to ensure that Pelican works smoothly with other tools.

### 3. Add Your Resume in Markdown

**Why Markdown?**  
Markdown is a simple markup language that is both human-readable and easy to write. It’s especially beneficial for technical writing because you can focus on content without worrying about complex formatting or code. Andrew Etter advocates for Markdown because it allows writers to produce clean and structured content that is easy to maintain and version control. With Markdown, you’ll ensure that your resume is easy to edit, update, and view across different platforms. 

1. Navigate to the `content/` folder and create a file named `resume.md`.
2. Write your resume using Markdown, like this:
   ```markdown
   Title: My Resume
   Date: 2025-03-01
   Category: Resume

   # My Resume
   **Name:** Your Name  
   **Email:** your.email@example.com  
   **LinkedIn:** [linkedin.com/in/yourname](https://linkedin.com/in/yourname)  
   **Experience:**
   - Job Title at Company Name
   - Another Job Title at Another Company
   - Pretty much everything you'd have in our regular resume
   ```

The use of headings, bold text, and links in Markdown helps make the resume more structured and easy to read, following Etter's advice on maintaining a clean and readable layout. More on that in the links section for Formatting in the addition resources section.

### 4. Generate the Static Site

**Why Generate the Static Site?**  
Once you've written your resume in Markdown, Pelican will convert it into a complete website that you can share with others. This process ensures that all content is properly formatted and ready to be deployed. It’s an essential step in creating a fully functional, static site that can be hosted on GitHub Pages.

1. To convert your Markdown file into HTML, run:
   ```bash
   pelican content
   ```
   This will generate your site’s HTML files inside the `output/` folder.
2. To preview your site locally before deployment, run:
   ```bash
   pelican content
   pelican --listen
   ```
   - Open your browser and go to `http://localhost:8000/` to preview your site.
   - This allows you to check how your resume looks before it’s published online, ensuring that everything is displayed correctly.

### 5. Deploy to GitHub Pages

**Why GitHub Pages?**  
GitHub Pages is a free and simple platform for hosting static websites. It allows you to easily deploy and share your website, making it perfect for hosting your resume. Once your resume is live on GitHub Pages, anyone can access it through a public URL.

1. Install `ghp-import` if you haven’t already:
   ```bash
   python -m pip install ghp-import
   ```
2. Deploy the website:
   ```bash
   ghp-import output -b gh-pages
   git push origin gh-pages
   ```
   This will deploy your site to the `gh-pages` branch on GitHub. The `gh-pages` branch is where GitHub Pages looks for content to serve.

3. Your resume is now live at `https://your-username.github.io/website-example`! This URL is your new public resume, accessible from anywhere.

---

## Additional Resources

To learn more, check out these resources:

1. [Pelican website-example](https://snipcart.com/blog/pelican-blog-tutorial-search-comments)
2. [Markdown Guide](https://commonmark.org/help/tutorial/)
3. [GitHub Pages Documentation](https://pages.github.com/)
4. [Mastering Markdown (GitHub)](https://guides.github.com/features/mastering-markdown/)

These resources will help you deepen your understanding of static site generators, Markdown, and GitHub Pages.

---

## FAQ

**Q: Can I preview my site before publishing?**  
A: Yes! To preview your site locally, run:
   ```bash
   pelican content
   pelican --listen
   ```
   Then visit `http://localhost:8000/` in your browser to preview your site.

**Q: How do I change my site’s theme?**  
A: Pelican supports custom themes. You can browse available themes at [Pelican Themes](https://github.com/getpelican/pelican-themes) and install one with:
   ```bash
   pelican-themes -i path/to/theme
   ```
   Then update `pelicanconf.py` to use the new theme.

**Q: Why am I getting a 404 error when trying to view my site?**  
A: Check the following:
   - Ensure the `gh-pages` branch is set as the source in GitHub Pages settings.
   - Make sure your repository is public.
   - Verify that you have correctly run `ghp-import` and pushed your changes.

---

## Credits

- Written by Oluwatofunmi Layi-Babatunde
- Based on *Modern Technical Writing* by Andrew Etter
- Resume template from [John Doe](https://www.overleaf.com/latex/templates/deedy-resume-reversed/hqnwfgjbbddt)
- Peer-reviewed by Kikiola Ojuko and Nataniella Ogogo
---

By following these steps, you’ll have your resume hosted online in no time. Happy coding!

---
