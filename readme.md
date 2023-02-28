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