# Vue 3 + TypeScript + Vite

Esta es una libreria de componentes desarrollada con vue 3 + vite

## Instalación

```
npm i squadmakers-vue-library
```

## Prueba local

Si quieres hacer pruebas locales con este repositorio, debes seguir los siguientes pasos:

1. ejecutar el comando `npm run link:watch`
  Este comando realizara el build del proyecto `vite build`, para hacer el link del proyecto `npm link` y asi
poder conectarse desde cualquier otro proyecto, para filnalmente realizar `vite build --watch` el cual detectara
cualquier camio que se haya realizado
2. En tu proyecto principal deberas ejecutar el comando `npm link squadmakers-vue-library` el cual realizara la conexion
con la libreria local.
3. Se deben importar los estilos y los componentes desde las siguientes rutas:
  ```
  import { SquadCard } from 'squadmakers-vue-library';
  @import '../../node_modules/squadmakers-vue-library/dist/style.css';
  ```

### Dependencies

This project use:
* Node 20.10.0
* Vue ^3.4.15

### More information
This project was carried out by [Javier Rodriguez](https://github.com/xjavierx1995) for a requested test using Vue 3 + vite. If you want to contact me, visit my [LinkedIn](https://www.linkedin.com/in/javier-rodr%C3%ADguez-93a61619a/).
