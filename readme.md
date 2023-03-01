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
Here's an example sass directory from a project structured in 7-1 architecture, as depicted in the Sass Guidelines article: https://sass-guidelin.es/#architecture

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
