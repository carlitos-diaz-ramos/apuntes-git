## Apuntes de `git` e `git-hub`

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
