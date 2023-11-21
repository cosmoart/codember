[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #02

**Mini Compiler Challenge**

En el mundo del espionaje, se utiliza un lenguaje de codificación con símbolos que realizan operaciones matemáticas simples.

Tu tarea es crear un mini compilador que interprete y ejecute programas escritos en este lenguaje de símbolos.

Las operaciones del lenguaje son las siguientes:

```bash
"#" Incrementa el valor numérico en 1.
"@" Decrementa el valor numérico en 1.
"*" Multiplica el valor numérico por sí mismo.
"&" Imprime el valor numérico actual.
```

El valor numérico inicial es 0 y las operaciones deben aplicarse en elorden en que aparecen en la cadena de símbolos.

**Ejemplos de entrada:**
```bash
Entrada: "##*&"
Salida esperada: "4"
Explicación: Incrementa (1), incrementa (2), multiplica (4), imprime (4).
```

```bash
Entrada: "&##&*&@&"
Salida esperada: "0243"
Explicación: Imprime (0), incrementa (1), incrementa (2), imprime (2), multiplica (4), imprime (4), decrementa (3), imprime (3).
```

**Tu desafío:**
Desarrolla un mini compilador que tome una cadena de texto y devuelva otra cadena de texto con el resultado de ejecutar el programa.

**Cómo resolverlo**
1. Resuelve el mensaje que encontrarás en este archivo: https://codember.dev/data/message_02.txt

2. Crea un programa al que le pases como entrada el mensaje anterior. Envía la salida con el comando "submit" en la terminal, por ejemplo así:
submit 024899488

## Solución

```js
function miniCompilador (input) {
	let value = 0;
	return input.split("&").slice(0, -1).reduce((acc, curr) => {
		[...curr].forEach(item => {
			if (item === "#") value++;
			if (item === "@") value--;
			if (item === "*") value *= value;
		})
		return acc += value;
	}, "");
}
```

## Respuesta

```bash
submit 024899455
```

[⬆️ Subir](#challengue-02)

[⬅️ Regresar](https://github.com/cosmoart/codember)
