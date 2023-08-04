# Apuntes de `git` e `git-hub`

## Empregar `git` localmente

Se non está feito xa, hai que establece-la información da conta
```
git config --global user.name "my-name"
git config --global user.email "my-name@gmail.com"
```

Supoñamos que temos unha carpeta `apuntes-git` con código e queremos empregar `git`.

En primeiro lugar iniciamos git:
```
git init -b main
```

Actualmente `git-hub` emprega `main` en vez de `master` como rama principal, así que cambiámo-lo nome para non ter problemas ó subir.

Podemos ve-lo estado da sincronización con
```
git status
```

Engadímolos tódolos ficheiros que queremos ter no sistema
```
git add *
```

Para crear un punto no que se salva o proxeto empregamos
```
git commit -m "First commit"
```

Cada vez que se fagan cambios hai que empregar `git add *` e cando se queira acompañar `git commit`.

Tamén convén crear un arquivo `.gitignore` especificando que arquivos non se van a controlar cada vez que se fai `git add *`.


## Subir código a un repositorio de `git-hub`

A continuación, na conta de `git-hub` creamos un repositorio novo (poñamos `apuntes-git`).  Deixa-lo repositorio completamente branco para evitar problemas.

Vinculámo-lo repositorio creado co local
```
git remote add origin https://github.com/blah/apuntes-git.git
```

Podemos ver que todo está ben con 
```
git remote -v
```

Para subi-los ficheiros utilizamos
```
git push -u origin main
```

Se refrescámo-la páxina de `git-hub` agora, xa deberían aparece-los arquivos locais tal e como estaban xusto despois do último `git commit`.

Cada vez que se queira sincronizar simplemente executamos 
```
git push origin main
```

despois de cada `git commit`.


## Crear unha bifurcación

O obxectivo de crear unha bifurcación é deixar activa a póla principal `main` mentres traballamos nalgo que é provisional ou que non estamos seguros de se vai saír.  Se máis adiante o novo traballo cremos que pode formar parte da versión principal, simplemente refundimos con `main`.

Para crear unha bifuración `testing` empregamos
```
git branch testing
```

e agora tecleamos
```
git checkout testing
```

para traballar nela (o que supón move-lo punteiro `HEAD` a esta nova bifurcación).

Neste momento empregamos os comandos habituais de `git` para ir actualizando esta bifurcación.  Cando consideremos que xa está rematado o noso traballo e queremos volver a `main`, temos que refundi-las dúas pólas.  En primeiro lugar volvemos a `main`.
```
git checkout main
```

Agora refundimos coa póla creada anteriormente:
```
git merge testing
```

Nótese que en ocasións refundir dúas pólas non vai ser tan sinxelo se traballamos simultaneamente nas dúas.  Neses casos haberá conflictos e haberá que resolvelos dalgún xeito.


## Referencias

- [Pro Git book](https://git-scm.com/book/en/v2).
- [Documentación de Git-hub](https://docs.github.com/en).
- [Vídeo introductorio](https://www.youtube.com/watch?v=RGOj5yH7evk).
- [Tutorial de Real Python](https://realpython.com/python-git-github-intro/).
- [Git en VSCode](https://code.visualstudio.com/docs/sourcecontrol/overview).
