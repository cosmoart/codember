[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #03

TMChein ya se está preparando para las fiestas y quiere empezar a decorar la casa con las luces de navidad.

Quiere comprar una pero sus favoritas son las que tienen dos colores que se van alternando. Como una zebra de dos colores.

Ha hecho que las luces sean Arrays y cada posición un color. Y quiere saber qué luces tienen las zebras más largas y cuál es el último color de esa sucesión de colores. Por ejemplo:

```
['red', 'blue', 'red', 'blue', 'green'] -> 4, blue
['green', 'red', 'blue', 'gray'] -> 2, gray
['blue', 'blue', 'blue', 'blue'] -> 1, blue
['red', 'green', 'red', 'green', 'red', 'green'] -> 6, green
['red, 'red, 'blue', 'red', 'red, 'red', 'green'] -> 3, red
```

Fíjate que sólo quiere saber la longitud de cuando dos colores se van alternando. Una vez que se rompe la alternancia de los dos colores, deja de contar.

Ahora que ya sabes esto, https://codember.dev/colors.txt

Recuerda:
- Una zebra de colores es cuando dos colores se alternan una y otra vez.
- Si se repite un color en la posición siguiente o es un tercer color, entonces se deja de contar.
- Lo que queremos calcular es la tira de colores más larga en forma de zebra y el último color de esa tira de colores.

Cómo enviar la solución:
- Usa el comando "submit" para enviar tu solución. Por ejemplo:

```bash
$ submit 62@red
```

## Solución

```js
const fs = require('fs')
const colors = JSON.parse(fs.readFileSync('./colors.json', 'utf8'))

let maxZebra = 1
let actualZebra = 1
let lastColor = colors[0]

colors.map((_, index) => {
	if (colors[index] === colors[index + 1]) return actualZebra = 1

	if (colors[index + 1] !== colors[index - 1]) return actualZebra = 2

	actualZebra++

	if (actualZebra >= maxZebra) {
		maxZebra = actualZebra
		lastColor = colors[index - 1]
	}
})

console.log(`${maxZebra}@${lastColor}`) // 30@red
```

## Respuesta

```bash
$ submit 30@red
```

[⬆️ Subir](#challengue-01)

[⬅️ Regresar](https://github.com/cosmoart/codember)
