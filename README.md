# Validación automática con GitHub Actions

![Validar script con ShellCheck](https://github.com/vrzafra/validacion-shellcheck/actions/workflows/validate.yml/badge.svg)

Este repositorio contiene un script de shell validado automáticamente con GitHub Actions y ShellCheck.

## Archivos principales

- `script.sh`: script de prueba en Bash.
- `.github/workflows/validate.yml`: workflow de GitHub Actions que ejecuta ShellCheck en cada push a la rama main.

## Funcionamiento

Cada vez que se suben cambios a la rama principal, GitHub Actions ejecuta automáticamente ShellCheck sobre el archivo `script.sh`.

Si el script no tiene errores, el workflow finaliza correctamente.  
Si ShellCheck detecta errores, el workflow falla y GitHub muestra el problema.
