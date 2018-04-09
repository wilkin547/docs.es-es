## <a name="introduction"></a>Introducción
Los cambios de redestinación afectan a las aplicaciones que se vuelven a compilar para tener como destino otra versión de .NET Framework. Son los siguientes:

* Cambios en el entorno en tiempo de diseño. Por ejemplo, las herramientas de compilación pueden emitir advertencias cuando antes no lo hacían.

* Cambios en el entorno en tiempo de ejecución. Estos solo afectan a las aplicaciones que tienen como destino específico la versión de .NET Framework redestinada. Las aplicaciones compiladas para versiones anteriores de .NET Framework se comportan de la misma manera que cuando se ejecutan en esas versiones.

En los temas en los que describen cambios de redestinación, hemos ordenado los elementos individuales por su impacto esperado, como sigue:

**Importante** Se trata de un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.

**Leve** Se trata de un cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.

**Caso específico** Se trata de un cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.

**Transparente** Se trata de un cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.
