# Apuntes de `git` e `git-hub`

## Empregar `git` localmente

Se non está feito xa, hai que establece-la información da conta

```
git config --global user.name "carlitos-diaz-ramos"
git config --global user.email "carlitos.diaz.ramos@gmail.com"
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
git commit -m "Acompañamento inicial"
```

Cada vez que se fagan cambios hai que empregar `git add *` e cando se queira acompañar `git commit`.

Tamén convén crear un arquivo `.gitignore` especificando que arquivos non se van a controlar cada vez que se fai `git add *`.


## Subir código a un repositorio de `git-hub`

A continuación, na conta de `git-hub` creamos un repositorio novo (poñamos `apuntes-git`).  Deixa-lo repositorio completamente branco para evitar problemas.

Vinculámo-lo repositorio creado co local

```
git remote add origin https://github.com/carlitos-diaz-ramos/apuntes-git.git
```

Podemos ver que todo está ben con 
```
git remote -v
```

Para subi-lo ficheiros utilizamos

```
git push -u origin main
```

Se refrescámo-la páxina de `git-hub` agora, xa deberían aparece-los arquivos locais tal e como estaban xusto despois do último `git commit`.

Cada vez que se queira sincronizar simplemente executamos 

```
git push origin main
```

despois de cada `git commit`.


