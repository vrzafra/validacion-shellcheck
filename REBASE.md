# Limpieza de commits con git rebase -i

## Objetivo

El objetivo de esta práctica es aprender a limpiar el historial de commits utilizando `git rebase -i`, mejorando la claridad y organización del repositorio.

## Situación inicial

Se crearon varios commits con mensajes poco descriptivos como:

- `arreglos`
- `cosas`
- `update`

Estos mensajes no aportaban información útil sobre los cambios realizados.

## Proceso realizado

Primero se visualizó el historial de commits con el siguiente comando:

```bash
git log --oneline
```

Después se ejecutó un rebase interactivo sobre los últimos tres commits:

```bash
git rebase -i HEAD~3
```

Durante el rebase interactivo se modificaron las acciones de los commits:

```text
reword dd7aa4c arreglos
squash 22d7618 cosas
squash 5f04ecf update
```

Se utilizó `reword` para cambiar el mensaje del commit principal y `squash` para fusionar los commits secundarios en uno solo.

A continuación, se escribió un nuevo mensaje de commit siguiendo la convención Conventional Commits:

```text
feat(script): añade nuevas líneas de salida en el script
```

## Resultado final

Tras finalizar el proceso, se comprobó el historial con:

```bash
git log --oneline
```

El resultado fue un historial más limpio, con un único commit representando los cambios realizados.

## Actualización del repositorio remoto

Como el rebase interactivo reescribe el historial, fue necesario actualizar el repositorio remoto usando:

```bash
git push --force-with-lease origin main
```

Se utiliza `--force-with-lease` en lugar de `--force` porque es una opción más segura: solo fuerza el push si nadie ha subido cambios nuevos al repositorio remoto mientras tanto.

## Conclusión

El uso de `git rebase -i` permite limpiar el historial de commits antes de subir o entregar un trabajo. Gracias a este proceso, los commits quedan mejor organizados, con mensajes más claros y siguiendo una convención profesional.
