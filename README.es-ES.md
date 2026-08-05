

# Napkin

![Captura de pantalla de Napkin](screenshot.png)

Napkin es una pequeña pizarra en blanco para macOS diseñada para el pensamiento rápido, el boceto y las notas de tinta primero. Te ofrece un lienzo amplio, colores de bolígrafo sencillos, un borrador, deshacer/rehacer, borrar el lienzo con opción de deshacer, exportación de imágenes, compatibilidad con Apple Sidecar y desplazamiento omnidireccional optimizado para tabletas de dibujo.

## Descarga

Descarga el último `Napkin.dmg` desde la página de Releases, ábrelo y arrastra `Napkin.app` a `Applications`.

Las compilaciones locales están firmadas de forma ad-hoc. La primera vez que abras una, macOS podría bloquearla porque no puede verificar al desarrollador. Si ocurre esto:

1. Abre `System Settings`.
2. Ve a `Privacy & Security`.
3. Busca el mensaje que indica que Napkin está bloqueado.
4. Haz clic en `Open Anyway`.

También puedes hacer clic derecho en `Napkin.app`, seleccionar `Open` y confirmar que deseas abrirlo.

## Características

- Lienzo amplio que comienza en el centro para que puedas desplazarte en cualquier dirección.
- Modo oscuro que intercambia el lienzo y el renderizado del bolígrafo principal sin modificar los datos de los trazos.
- Preferencia persistente para el modo predeterminado en la configuración.
- Bolígrafos en negro, azul, rojo y verde.
- Borrador con vista previa del cursor.
- Deshacer y rehacer, incluido deshacer la acción de Borrar.
- Exporta el lienzo visible o el área dibujada completa como PNG.
- Funciona con Apple Sidecar para hacer bocetos desde un iPad.
- Mantén presionado el clic derecho o el clic central y aleja el puntero del punto de inicio para desplazarte continuamente.

## Compilar desde el código fuente

Requisitos:

- macOS 13 o posterior
- Swift 6 o posterior
- Herramientas de línea de comandos de Xcode

Ejecuta la aplicación directamente:

```sh
swift run Napkin
```

Crea un paquete `.app`:

```sh
scripts/build-app.sh
open .build/Napkin.app
```

Crea un `.dmg` de lanzamiento:

```sh
scripts/package-dmg.sh
open .build/Napkin.dmg
```

Crea un `.dmg` de lanzamiento distribuible y notariado:

```sh
CODESIGN_IDENTITY="Developer ID Application: Your Name (TEAMID)" \
NOTARYTOOL_PROFILE="napkin-notary" \
scripts/package-dmg.sh
```

También puedes proporcionar las credenciales de notarización directamente mediante `APPLE_ID`, `APPLE_TEAM_ID` y `APPLE_APP_PASSWORD`.

## Estado

Napkin es un software en etapa temprana. Es intencionalmente pequeño, funciona solo de forma local y se centra en el ciclo de dibujo.

## Código fuente

El código fuente está disponible en [github.com/alex-k03/napkin](https://github.com/alex-k03/napkin).

## Autor

Creado por Alexander Kharchenko.

## Licencia

Napkin es software de código abierto publicado bajo la Licencia MIT. Consulte [LICENSE](LICENSE).
