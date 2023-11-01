[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #05

Hay tanto framework y biblioteca que ya no sabemos qué usar. Así que un comité ha decidido hacer una especie de Los Juegos del Hambre para decidir qué tecnología se queda.

Ha puesto todas las tecnologías en círculo de forma aleatoria. La tecnología en el índice 0 empieza matando a la que tiene justo a la derecha (índice + 1).

El siguiente turno es para la tecnología que esté viva que queda a la derecha de la que se acaba de morir. Y así sucesivamente hasta que sólo quede una. Mira este ejemplo de un grupo de 10 tecnologías, paso a paso:

```
         5
      6     4
   7           3
   8           2
      9     1
         0

0 mata a 1
2 mata a 3
4 mata a 5
6 mata a 7
8 mata a 9

         X
     6      4
   X           X
   8           2
      X     X
         0

0 mata a 2
4 mata a 6
8 mata a 0

         X
     X      4
   X           X
   8           X
      X     X
         X

4 mata a 8

         X
     X      4
   X           X
   X           X
      X     X
         X
```

La tecnología en el índice 4 es la que ha sobrevivido.

Ahora, para probar que somos capaces de crear un algoritmo que funcione, tenemos la lista de mecenas de la comunidad de midudev: https://codember.dev/mecenas.json

Tienes que crear un algoritmo que nos diga qué usuario sobreviviría usando el mismo sistema.

Cómo enviar la solución:
- Envía la solución con el comando submit, y el índice de la persona que sobrevive y su nombre de usuario, separado de un guión.

Por ejemplo, si el usuario que sobrevive es facundopacua y está en el índice 8 sería:

```bash
$ submit facundocapua-8
```

## Solución

```js
const ls = require('fs')
const data = JSON.parse(ls.readFileSync('./mecenas.json', 'utf8'))

let mecenas = data.map((m, i) => m = m + "-" + i)

while (mecenas.length > 1) {
	mecenas.forEach((_, i) => {
		if (i == mecenas.length - 1) mecenas.splice(0, 1)
		else mecenas.splice(i + 1, 1)
	});
}

console.log(mecenas[0]) // Diana-100
```

## Respuesta

```bash
$ submit Diana-100
```

[⬆️ Subir](#challengue-05)

[⬅️ Regresar](https://github.com/cosmoart/codember)
