# Initialisation du projet
```
npm init
```
Création du package.json

# Installation de Gulp
```
sudo npm install -g gulp-cli
sudo npm install --save-dev gulp 
```

#### Il se peut qu'un probème avec xcode survienne

executer les commande suivantes : 
```
sudo rm -rf $(xcode-select -print-path)
xcode-select --install
```


# Installation du plugin TYPESCRIPT
```
sudo npm install --save-dev typescript gulp-typescript
```

# Configuration

Créer un fichier gulpfile.js

puis se rendre sur :

> https://github.com/ivogabe/gulp-typescript/blob/master/gulpfile.js

inserer les lignes suivantes et adapter en fonction de la structure du projet :

```
var gulp = require('gulp');
var ts = require('gulp-typescript');

gulp.task('default', function () {
    return gulp.src('src/**/*.ts')
        .pipe(ts({
            noImplicitAny: true,
            outFile: 'output.js'
        }))
        .pipe(gulp.dest('built/local'));
});
```

pour finir il faut executer la tâche Gulp qui compilera le code :

```
gulp default
```

# Executer du code dans node
```
node dist/bundle.js
```

# Creéation d'un bundle

avec browserify, tsfy, vinyl-source-stream

```
npm install --save-dev browserify tsify vinyl-source-stream
```