[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #05

**El problema final**
Finalmente los hackers han conseguido acceder a la base de datos y la han dejado corrupta. Pero parece que han dejado un mensaje oculto en la base de datos. ¿Podrás encontrarlo?

Nuestra base de datos está en formato .csv. Las columnas son id, username, email, age, location.

Un usuario sólo es válido si:

- id: existe y es alfanumérica
- username: existe y es alfanumérico
- email: existe y es válido (sigue el patrón user@dominio.com)
- age: es opcional pero si aparece es un número
- location: es opcional pero si aparece es una cadena de texto

Ejemplos:

```js
Entrada: 1a421fa,alex,alex9@gmail.com,18,Barcelona
Resultado: ✅ Válido

Entrada: 9412p_m,maria,mb@hotmail.com,22,CDMX
Resultado: ❌ Inválido (id no es alfanumérica, sobra el _)

Entrada: 494ee0,madeval,mdv@twitch.tv,,
Resultado: ✅ Válido (age y location son opcionales)

Entrada: 494ee0,madeval,twitch.tv,22,Montevideo
Resultado: ❌ Inválido (email no es válido)
```

** Cómo resolverlo **
1. Analiza la lista de entradas de la baes de datos y detecta los inválidos: https://codember.dev/data/database_attacked.txt

2. Encuentra el primer caracter (número o letra) del username de cada usuario inválido. Júntalos por orden de aparición y descubre el mensaje oculto. Luego envíalo con submit. Por ejemplo:
submit att4ck

## Solución

```js
function encontrarCaracterInvalido (datos) {
	return datos.reduce((usuariosInvalidos, fila) => {
		const columnas = fila.split(',');

		const id = columnas[0].trim();
		const username = columnas[1].trim();
		const email = columnas[2].trim();
		const age = columnas[3] ? columnas[3].trim() : '';
		const location = columnas[4] ? columnas[4].trim() : '';

		if (!/^[a-zA-Z0-9]+$/.test(id) ||
			!/^[a-zA-Z0-9]+$/.test(username) ||
			!/^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/.test(email) ||
			(age !== '' && isNaN(age)) ||
			(location !== '' && typeof location !== 'string')) {
			usuariosInvalidos.push(username[0]);
		}

		return usuariosInvalidos;
	}, []).join('');
}
```

## Respuesta

```bash
submit youh4v3beenpwnd
```

[⬆️ Subir](#challengue-05)

[⬅️ Regresar](https://github.com/cosmoart/codember)
