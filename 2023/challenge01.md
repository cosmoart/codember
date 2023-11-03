[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #01

Un espía está enviando mensajes encriptados.

Tu misión es crear un programa que nos ayude a buscar patrones...

Los mensajes son palabras separadas por espacios como este:
gato perro perro coche Gato peRRo sol

Necesitamos que el programa nos devuelva el número de veces que aparece cada palabra en el mensaje, independientemente de si está en mayúsculas o minúsculas.

El resultado será una cadena de texto con la palabra y el número de veces que aparece en el mensaje, con este formato:
``gato2perro3coche1sol1``

¡Las palabras son ordenadas por su primera aparición en el mensaje!

** Más ejemplos: **
```bash
llaveS casa CASA casa llaves -> llaves2casa3
taza ta za taza -> taza2ta1za1
casas casa casasas -> casas1casa1casas1
```

## Solución

```js
function contarPalabras (mensaje) {
	return mensaje.toLowerCase().split(" ").reduce((acc, palabra) => {
		if (acc.includes(palabra)) acc[acc.indexOf(palabra) + 1] += 1;
		else acc.push(palabra, 1);
		return acc;
	}, []).join("");
}
```

## Respuesta

```bash
submit murcielago15leon15jirafa15cebra6elefante15rinoceronte15hipopotamo15ardilla15mapache15zorro15lobo15oso15puma2jaguar14tigre10leopardo10gato12perro12caballo14vaca14toro14cerdo14oveja14cabra14gallina10pato10ganso10pavo10paloma10halcon11aguila11buho11colibri9canario8loro8tucan8pinguino7flamenco7
```

[⬆️ Subir](#challengue-01)

[⬅️ Regresar](https://github.com/cosmoart/codember)
