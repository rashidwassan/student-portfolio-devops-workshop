# Student Portfolio - DevOps Workshop

A beginner-friendly portfolio website project designed to help students learn Git, GitHub, and DevOps practices through hands-on experience.

## 📝 Project Purpose

This project serves as a practical introduction to:
- Building a simple, professional portfolio website using HTML and CSS
- Learning essential Git workflows and version control
- Understanding the basics of collaborative development
- Preparing for CI/CD integration using GitHub Actions (to be added in the workshop)

## 🎯 Features

- **Clean and Modern Design**: Professional layout with smooth animations and transitions
- **Responsive**: Works seamlessly on desktop, tablet, and mobile devices
- **Easy to Customize**: Simple structure that students can easily modify
- **Sections Include**:
  - Hero section with profile picture
  - About Me section with skills showcase
  - Projects portfolio grid
  - Contact section with social links
  - Sticky navigation bar

## 🚀 Getting Started

### Prerequisites

- A web browser (Chrome, Firefox, Safari, or Edge)
- Git installed on your computer ([Download Git](https://git-scm.com/downloads))
- A text editor (VS Code, Sublime Text, or Notepad++)
- A GitHub account ([Sign up here](https://github.com/join))

### Setup Instructions

1. **Clone the repository** to your local machine:
   ```bash
   git clone https://github.com/rashidwassan/student-portfolio-devops-workshop.git
   cd student-portfolio-devops-workshop
   ```

2. **Open the project** in your text editor

3. **View the website** by opening `index.html` in your web browser

## ✏️ Customization Guide

### Personalizing Your Portfolio

1. **Update Personal Information** (`index.html`):
   - Replace "Your Name" with your actual name
   - Update the hero subtitle with your title/role
   - Modify the about section with your own bio
   - Add your actual email and social media links

2. **Add Your Profile Picture** (`assets/profile.jpg`):
   - Replace the placeholder image with your own photo
   - Keep the filename as `profile.jpg` or update the reference in `index.html`
   - Recommended size: 400x400 pixels (square format)

3. **Showcase Your Projects**:
   - Edit the project cards in the Projects section
   - Add project descriptions, technologies used, and links
   - You can add more project cards by copying the existing structure

4. **Customize Skills**:
   - Update the skill tags in the About section
   - Add or remove skills based on your expertise

5. **Styling** (`style.css`):
   - Change colors by modifying the color values (e.g., `#667eea`, `#3498db`)
   - Adjust fonts by changing the `font-family` property
   - Modify spacing, sizes, and other visual elements as desired

## 📚 Basic Git Workflow

Once you've customized your portfolio, use these Git commands to save and share your changes:

### 1. Check Status
See which files you've modified:
```bash
git status
```

### 2. Stage Your Changes
Add files to be committed:
```bash
# Add specific files
git add index.html style.css

# Or add all changes
git add .
```

### 3. Commit Your Changes
Save your changes with a descriptive message:
```bash
git commit -m "Personalize portfolio with my information"
```

### 4. Push to GitHub
Upload your changes to GitHub:
```bash
git push origin main
```

### Additional Useful Commands

- **Create a new branch** for experimenting:
  ```bash
  git checkout -b my-new-feature
  ```

- **Switch between branches**:
  ```bash
  git checkout main
  ```

- **View commit history**:
  ```bash
  git log --oneline
  ```

- **Pull latest changes** from GitHub:
  ```bash
  git pull origin main
  ```

## 🔄 Automated Deployment with GitHub Actions

This section will guide you through setting up automated deployment of your portfolio website to GitHub Pages using GitHub Actions. Once configured, your website will automatically update whenever you push changes to your repository!

### What is GitHub Actions?

GitHub Actions is a continuous integration and continuous deployment (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. Every time you push code to your repository, GitHub Actions can automatically deploy your website to GitHub Pages.

### Step-by-Step Setup Guide

#### Step 1: Create the GitHub Actions Workflow File

1. In your repository, create a new directory structure: `.github/workflows/`
   ```bash
   mkdir -p .github/workflows
   ```

2. Inside the `workflows` folder, create a new file named `deploy.yml`

3. Copy and paste the following code into `deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main  # Triggers deployment when you push to the main branch
  workflow_dispatch:  # Allows you to manually trigger the workflow from GitHub UI

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4
        
      - name: Setup Pages
        uses: actions/configure-pages@v4
        
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          # Upload entire repository
          path: '.'
          
  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

#### Step 2: Enable GitHub Pages in Repository Settings

1. Go to your GitHub repository in your web browser
2. Click on **Settings** (top right of the repository page)
3. In the left sidebar, click on **Pages** (under "Code and automation")
4. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"
5. Save the changes

#### Step 3: Push Your Workflow to GitHub

After creating the workflow file, commit and push it to your repository:

```bash
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Actions workflow for automated deployment"
git push origin main
```

#### Step 4: Verify Deployment

1. Go to the **Actions** tab in your GitHub repository
2. You should see your workflow running
3. Once complete (green checkmark ✓), go to **Settings** > **Pages**
4. You'll see your published site URL (e.g., `https://yourusername.github.io/student-portfolio-devops-workshop/`)
5. Click the URL to view your live portfolio!

### Understanding the Workflow

Here's what each part of the workflow does:

- **`on: push`**: Triggers the workflow automatically when you push to the main branch
- **`workflow_dispatch`**: Allows you to manually run the workflow from GitHub's UI
- **`permissions`**: Grants necessary permissions to deploy to GitHub Pages
- **`build` job**: Prepares your website files for deployment
- **`deploy` job**: Publishes your site to GitHub Pages

### Making Updates

After setup, deploying updates is easy:

1. Make changes to your `index.html`, `style.css`, or other files
2. Commit and push your changes:
   ```bash
   git add .
   git commit -m "Update portfolio content"
   git push origin main
   ```
3. GitHub Actions automatically deploys your changes
4. Your live site updates in 1-2 minutes!

### Troubleshooting

**Workflow fails to run:**
- Ensure the workflow file is in `.github/workflows/` directory
- Check that the file is named with `.yml` or `.yaml` extension
- Verify you've selected "GitHub Actions" as the source in Pages settings

**Site not updating:**
- Check the Actions tab for errors
- Ensure your push was to the `main` branch
- Wait a few minutes for GitHub's CDN to update

**404 Error on site:**
- Verify GitHub Pages is enabled in Settings
- Check that the workflow completed successfully
- Ensure your repository is public (or you have GitHub Pro/Team for private repos)

### Benefits of Automated Deployment

✅ **No manual deployment needed** - Push code and it's live automatically  
✅ **Always in sync** - Your live site always matches your repository  
✅ **Version history** - Every deployment is tracked in your commit history  
✅ **Free hosting** - GitHub Pages is free for public repositories  
✅ **Professional workflow** - Learn industry-standard CI/CD practices

## 📁 Project Structure

```
student-portfolio-devops-workshop/
│
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions workflow for automated deployment
├── assets/             # Folder for images and media
│   └── profile.jpg     # Placeholder profile picture
├── index.html          # Main HTML file with portfolio structure
├── style.css           # CSS file with all styling
└── README.md           # Project documentation (this file)
```

## 💡 Tips for Students

1. **Start Small**: Make one change at a time and test it
2. **Use Git Often**: Commit your changes frequently with clear messages
3. **Experiment**: Try changing colors, fonts, and layouts to learn
4. **Ask Questions**: Don't hesitate to ask for help when stuck
5. **Have Fun**: This is your portfolio - make it unique and reflect your personality!

## 🤝 Contributing

This project is designed for educational purposes. Feel free to:
- Fork the repository
- Create your own version
- Share improvements and suggestions
- Help other students learn

## 📄 License

This project is open source and available for educational use.

## 🙋 Need Help?

- Check the code comments in `index.html` and `style.css`
- Review Git documentation: https://git-scm.com/doc
- Explore HTML/CSS tutorials: https://developer.mozilla.org/

---

**Happy Coding!** 🚀 Remember, every expert was once a beginner. Keep learning and practicing!