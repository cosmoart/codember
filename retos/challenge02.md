[⬅️ Regresar](https://github.com/cosmoart/codember)

# Challengue #02

Un grupo de ciber criminales están usando mensajes encriptados para comunicarse. El FBI nos ha pedido ayuda para descifrarlos.

Los mensajes son cadenas de texto que incluyen números enteros muy largos y espacios en blanco. Aunque los números no parecen tener sentido... una chica llamada Alice ha descubierto que podrían usar el código ASCII de las letras en minúscula.

Con su método ha conseguido descifrar estos mensajes:

```
"109105100117" -> midu
"9911110010110998101114" -> codember
"9911110010110998101114 109105100117" -> codember midu
"11210897121 116101116114105115" -> play tetris
```

Pero han interceptado un mensaje más largo que no han podido y nos han dicho que es muy importante que lo descifremos:

`11610497110107115 102111114 11210897121105110103 9911110010110998101114 11210810197115101 11510497114101`

Pistas:
- Recuerda que los mensajes son cadenas de texto conformadas por números y espacios en blanco.
- Parece que los números tienen algo que ver con el código ASCII.
- Los espacios en blanco parece que son simplemente espacios...

Cómo enviar la solución
- Usa el comando "submit" para enviar tu solución con la frase descifrada, en minúsculas y respetando los espacios en blanco. Por ejemplo: `$ submit this is fine`

## Solución

```js
const ENCRYPTED = "11610497110107115 102111114 11210897121105110103 9911110010110998101114 11210810197115101 11510497114101"

const wordCharacters = ENCRYPTED.match(/1\d{2}|9\d{1}/g)

let message = String.fromCharCode(...wordCharacters)

console.log(message) // thanksforplayingcodemberpleaseshare
```

## Respuesta

```bash
$ submit thanks for playing codember please share
```

[⬆️ Subir](#challengue-01)

[⬅️ Regresar](https://github.com/cosmoart/codember)
