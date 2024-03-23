Install vscode and node 
check whether node is istalled successfully by node -v
In extensions icon search for live server and install it and click on settings button in liveserver and type "full reload " after it
now type "npx tailwindcss init" (will create tailwind config file => tailwindconfig.js)
now create build directory and in that create index.html file
and create src directory and in that create input.css file
In tailwindconfig.js file , inside content we need to add html files and js files that we are going to use for eg.,('./build/*.html' , './build/*.js')
in Input.css file add all the @tailwind libraries (@tailwind base,components and utilities)(---inorder to remove warnings inside preferences => settings => unknown and ignore it)
In terminal type npx tailwind -i ./src/input.css -o ./build/css/style.css  (==> it will create style.css file in css folder in build directory)
LInk this style.css file inside index.html file
// NOw we can write all the code in index.html file & input.css files and we create all the necessary files

Now type npm init -y  (will create package.json files)

Everytime it is difficult to type " npx tailwind -i ./src/input.css -o ./build/css/style.css --watch"  so inorder to avoid that in package.json file under scripts type 
"tailwind": "npx tailwindcss -i ./src/input.css -o ./build/css/style.css --watch",

and for prettier inside package.json file type:
"prettier": "npx prettier --write ./build/*.html"


for installing dev dependency i.e., prettier here:
npm i -D prettier-plugin-tailwindcss

now we will get node_modules folder also 
inside .gitignore file add node_modules

==> from now inorder to run the application we can type npm run tailwind 

Inside tailwind.config.js file add 
screens : {
        'widescreen' : { 'raw' : '(min-aspect-ratio: 3/2)'},
        'tallscreen' : { 'raw' : '(max-aspect-ratio: 13/20)'},

      },
 keyframes: {
        'open-menu': {
          '0%': { transform: 'scaleY(0)'},
          '80%': { transform: 'scaleY(1.2)'},
          '100%': { transform: 'scaleY(1)'},

        },
      },
animation: {
        'open-menu': 'open-menu 0.5s ease-in-out forwards',
      }

==> now in terminal type  npm run prettier

If there are any errors clear those and run the command again.
now we can push these chanbges to github

git init
git add .
git status
git commit -m "commit message"
git remote add origin https://github.com/SaiSitaTulasi/Tailwind.git(link of our repo on github)
git branch -M main
git push -u origin master


