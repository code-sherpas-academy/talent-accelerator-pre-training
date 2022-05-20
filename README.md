# Talent Accelerator Pre-training

## Exercise 1: Programming languages popularity

Los objetivos de este ejercicio son:
- contribuir en un repositorio compartido por un equipo de desarrollo.
- entender qué es un conflicto en git, cuándo se provocan y cómo se resuelven.

Tenemos que rellenar la siguiente tabla de popularidad de lenguajes de programación. Por cada lenguaje, tenemos que consultar sus índices de popularidad en [TIOBE Index](https://www.tiobe.com/tiobe-index/) y [IEEE Spectrum ranking](https://spectrum.ieee.org/top-programming-languages/) y actualizarlos en la tabla.

|    Author    |  Programming language  | TIOBE index | IEEE Spectrum ranking  |
|:------------:|:----------------------:|:-----------:|:----------------------:|
|   Alfonso    |       Javascript       |    0.0%     |          0.0           |
|    Álvaro    |         Python         |    0.0%     |          0.0           |
|   Augusto    |          Java          |    0.0%     |          0.0           |
|    Darío     |           C            |    0.0%     |          0.0           |
|    Davina    |          C++           |    0.0%     |          0.0           |
|    Denise    |           C#           |    0.0%     |          0.0           |
|  Juan Diego  |           R            |    0.0%     |          0.0           |
|   Julieta    |          PHP           |    0.0%     |          0.0           |
|    Kevin     |           Go           |    0.0%     |          0.0           |
|    Lucía     |         Delphi         |    0.0%     |          0.0           |
|   Macarena   |      Objective-C       |    0.0%     |          0.0           |
|    Matias    |          Perl          |    0.0%     |          0.0           |
|   Natalia    |          Ruby          |    0.0%     |          0.0           |
|   Victoria   |          Rust          |    0.0%     |          0.0           |
|              |         Kotlin         |    0.0%     |          0.0           |
|              |         Scala          |    0.0%     |          0.0           |
|              |        Haskell         |    0.0%     |          0.0           |
|              |      Visual Basic      |    0.0%     |          0.0           |
|              |          Lua           |    0.0%     |          0.0           |
|              |        Clojure         |    0.0%     |          0.0           |
|              |          Lisp          |    0.0%     |          0.0           |
|              |         Prolog         |    0.0%     |          0.0           |
|              |         Swift          |    0.0%     |          0.0           |

Cada uno de vosotros tiene que hacer lo siguiente para su línea (ver columna _Author_):
1. Crea dos ramas a partir de la principal. Una para actualizar el índice TIOBE, y otra para el otro índice. _Elige unos nombres para tus ramas que expresen sin lugar a dudas qué casilla de la tabla se va a modificar. Piensa que tus compañeros también van a crear otras 2 ramas. Tendríamos que poder ver todos los nombres de las ramas en una lista y saber relacionarlas sin dificultad con la casilla de la tabla que va a modificar._
2. Ve a la rama de TIOBE y modifica el valor de la casilla con el valor que has encontrado en la web.
3. Haz commit del cambio con un mensaje descriptivo (ver [Cómo escribir un buen mensaje de _commit_](https://cbea.ms/git-commit/))
4. Haz push de tu cambio
5. Ve a la página web de este repositorio y crea una pull request desde tu rama hacia la rama _main_.
6. Acepta la pull request tu misma/o para que se integren los cambios en main.
   1. Vuelve a hacer los pasos del 3 al 6 para hacer lo mismo pero con la rama de "IEEE Spectrum ranking". Si todo ha salido como esperamos, no habrás podido completar el paso 7. Esto se debe a que estás intentando modificar la misma línea que se ha modificado en _main_ y que aún no te has descargado en tu rama.
7. Haz pull de _main_ hacia tu rama para resolver el conflicto y decidir cómo debe quedar la línea finalmente. Hazlo con el terminal de comandos.
8. Cuando lo hayas conseguido, vuelve a repetir el proceso para provocar un conflicto, pero esta vez grábalo en video mientras lo explicas y grabas tu pantalla. Si no tienes experiencia grabando videos, te recomendamos una opción sencilla y rápida que es usar la aplicación [Zoom](https://zoom.us/). Crea una videollamada donde estés tu sola/o, comparte tu pantalla y empieza a grabar la videollamada. Esta vez puedes intentar hacerlo con la ayuda de alguna herramienta gráfica como un IDE para que veas la diferencia en la experiencia de resolver un conflicto de git.
