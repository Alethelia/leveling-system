# Flujo de trabajo con Git – Leveling System

Este archivo describe el flujo de trabajo recomendado para el proyecto Leveling System.

## Ramas principales

- **main**: Rama principal y estable. Aquí solo debe estar el código listo para producción.
- **dev**: Rama de desarrollo. Aquí se integran las nuevas funcionalidades antes de pasarlas a main.

## Ramas secundarias

- **feature/***: Ramas temporales para nuevas funciones o mejoras. Ejemplos:
  - feature/ia-sugerencias
  - feature/front-tester
  - feature/cerebro-modulo

- **hotfix/***: Ramas para corregir errores críticos en producción. Ejemplos:
  - hotfix/fix-xp-calculation

## Flujo recomendado

1. Crear rama de desarrollo (solo la primera vez):
```bash
git checkout -b dev
git push -u origin dev
```

2. Crear rama de funcionalidad:
```bash
git checkout -b feature/nombre-funcionalidad
```

3. Realizar los cambios, confirmar y subir:
```bash
git add .
git commit -m "Descripción clara del cambio"
git push -u origin feature/nombre-funcionalidad
```

4. Una vez terminada la funcionalidad, integrarla a dev:
```bash
git checkout dev
git pull
git merge feature/nombre-funcionalidad
git push
```

5. Cuando el proyecto en dev esté estable, integrarlo a main:
```bash
git checkout main
git pull
git merge dev
git push
```

## Comandos útiles

Ver ramas existentes:
```bash
git branch
```

Cambiar de rama:
```bash
git checkout nombre-rama
```

Eliminar una rama local:
```bash
git branch -d nombre-rama
```

Eliminar una rama remota:
```bash
git push origin --delete nombre-rama
```

## Recomendación

No trabajes directamente en la rama main. Utiliza dev y ramas feature para un flujo de trabajo limpio y ordenado.
