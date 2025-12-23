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

## 🔄 CI/CD Integration (Coming Soon)

During the DevOps workshop, we will add:
- **GitHub Actions workflows** for automated deployment
- **Automated testing** to verify code quality
- **Continuous Deployment** to publish your portfolio automatically
- **Build processes** and optimization

Stay tuned for these advanced features that will automate your development workflow!

## 📁 Project Structure

```
student-portfolio-devops-workshop/
│
├── index.html          # Main HTML file with portfolio structure
├── style.css           # CSS file with all styling
├── assets/             # Folder for images and media
│   └── profile.jpg     # Placeholder profile picture
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