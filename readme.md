# Produce maintainable CSS stylesheets with SASS
CSS is the palette we use to paint the web, making pages beautiful, identifiable, and responsive. We’ll learn to write clean, maintainable, and modular CSS code through the implementation of designed naming and file structures, such as BEM, and the use of SASS, a CSS precompiler.

# Install Node.js
https://nodejs.org/en/

# Check Node
node -v   
to verify if Node is well installed and to know the version.

# Check npm
npm -v  
to verify if npm is well installed and to know the version.

# Initialize package.json
npm init  
then press Enter and fill (or not: Enter) the fields

# Test
npm run test

# Install Sass
npm install -g sass

# Check Sass
sass --version

# Create a script
"scripts": {  
 "sass": "sass --watch ./sass/main.scss:./public/css/style.css"  
},

sass  tells to npm where to find the script to execute ;  
--watch  is a flag (option) used by npm to find eventual changes in Sass file. If it find one, it will compile and update Sass file ;  
./sass/main.scss  tells to the script in node-sass where to find the Sass file to compile ;  
colon (:) splits source path and destination path ;  
./css/style.css  tells to the script where to compile CSS and how name it.

# Run Sass
npm run sass

# 4 output styles
nested (the default) indents CSS rules to match the nesting of the Sass source.  
expanded writes each selector and declaration on its own line.  
compact puts each CSS rule on its own single line.  
compressed removes as many extra characters as possible, and writes the entire stylesheet on a single line.  

# Use of flag style
--style + name  
Ex: "scripts": {  
    "sass": "sass --watch ./sass/main.scss:./public/css/style.css --style compressed"  
  },
  
# 7-1 pattern
Here's an example sass directory from a project structured in 7-1 architecture, as depicted in the Sass Guidelines article :   
https://sass-guidelin.es/#architecture  

sass/  
|  
|– abstracts/  
|   |– _variables.scss    # Sass Variables  
|   |– _functions.scss    # Sass Functions  
|   |– _mixins.scss       # Sass Mixins  
|   |– _placeholders.scss # Sass Placeholders  
|  
|– base/  
|   |– _reset.scss        # Reset/normalize  
|   |– _typography.scss   # Typography rules  
|   …                     # Etc.  
|  
|– components/  
|   |– _buttons.scss      # Buttons  
|   |– _carousel.scss     # Carousel  
|   |– _cover.scss        # Cover  
|   |– _dropdown.scss     # Dropdown  
|   …                     # Etc.  
|  
|– layout/  
|   |– _navigation.scss   # Navigation  
|   |– _grid.scss         # Grid system  
|   |– _header.scss       # Header  
|   |– _footer.scss       # Footer  
|   |– _sidebar.scss      # Sidebar  
|   |– _forms.scss        # Forms  
|   …                     # Etc.  
|  
|– pages/  
|   |– _home.scss         # Home specific styles  
|   |– _contact.scss      # Contact specific styles  
|   …                     # Etc.  
|  
|– themes/  
|   |– _theme.scss        # Default theme  
|   |– _admin.scss        # Admin theme  
|   …                     # Etc.  
|  
|– vendors/  
|   |– _bootstrap.scss    # Bootstrap  
|   |– _jquery-ui.scss    # jQuery UI  
|   …                     # Etc.  
|  
`– main.scss              # Main Sass file  

# Install Autoprefixer, PsstCSS & PostCSS-CLI
Autoprefixer is a PostCSS plugin which parse your CSS and add vendor prefixes using the Can I Use database (https://caniuse.com/) to determine which prefixes are needed.

npm install autoprefixer postcss postcss-cli -g

# Add Autoprefixer script
1. Add a new script named "prefix" :
"scripts": {
 "sass": "sass ./sass/main.scss:./public/css/style.css -w --style compressed",
 "prefix":
}

2. Tell to npm to use the new postcss package, and where to fin the CSS compiled file :
"prefix": "postcss ./public/css/style.css"

3. Tell to postcss package to use Autoprefixer with flag --use + autoprefixer :
"prefix": "postcss ./public/css/style.css --use autoprefixer"

4. Tell where to put the new prefixed CSS file :
"prefix": "postcss ./public/css/style.css --use autoprefixer -d ./public/css/prefixed/"

# Tell to Autoprefixer which versions to verify
1. Add a new key named "browserslist" :
"scripts": {
   "prefix": "postcss ./public/css/style.css --use autoprefixer -d ./public/css/prefixed/"
},
"author": "",
"license": "ISC",
"browserslist": 

2. Specify versions
Ex: "browserslist": "last 4 versions"

# Run Autoprefixer
npm run prefix
-> prefixed folder is created with style.css file inside with prefix lines added automatically.