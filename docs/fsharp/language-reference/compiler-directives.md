---
title: Directivas de compilador
description: Obtenga información sobre F# las directivas de preprocesador de lenguaje, directivas de compilación condicional, las directivas de línea y las directivas de compilador.
ms.date: 12/10/2018
ms.openlocfilehash: 3fade7407f84b00163bd5b3d7774104bce8a25af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766108"
---
# <a name="compiler-directives"></a>Directivas de compilador

En este tema se describen las directivas de procesador y las directivas de compilador.

## <a name="preprocessor-directives"></a>Directivas de preprocesador

Una directiva de preprocesador tiene como prefijo el símbolo # y aparece en una línea independiente. La interpreta el preprocesador, que se ejecuta antes que el compilador.

En la siguiente tabla se recoge una lista de las directivas de preprocesador disponibles en F#.

|Directiva|Descripción|
|---------|-----------|
|`#if` *Símbolo*|Admite la compilación condicional. Código de la sección después de la `#if` se incluye si el *símbolo* está definido. El símbolo también se puede negar con `!`.|
|`#else`|Admite la compilación condicional. Marca una sección de código que incluir si el símbolo usado con la directiva `#if` anterior no se ha definido.|
|`#endif`|Admite la compilación condicional. Marca el final de una sección condicional de código.|
|`#`[línea] *int*,<br/>`#`[línea] *int* *cadena*,<br/>`#`[line] *int* *verbatim-string*|Indica el nombre de archivo y la línea de código fuente original para la depuración. Esta característica se proporciona para las herramientas que generan código fuente de F#.|
|`#nowarn` *warningCode*|Deshabilita una o varias advertencias del compilador. Para deshabilitar una advertencia, encuentre su número correspondiente en los resultados del compilador e inclúyalo entre comillas. Omita el prefijo "FS". Para deshabilitar varios números de advertencia en la misma línea, incluya cada número entre comillas y separe cada cadena con un espacio. Por ejemplo:

`#nowarn "9" "40"`

El efecto de deshabilitar una advertencia que se aplica a todo el archivo, incluidas las partes del archivo que preceden a la directiva. |

## <a name="conditional-compilation-directives"></a>Directivas de compilación condicional

Código que está desactivada de forma una de estas directivas aparece atenuado en el Editor de código de Visual Studio.

> [!NOTE]
> El comportamiento de las directivas de compilación condicional no es el mismo que en otros idiomas. Así, no se pueden usar expresiones booleanas con símbolos, mientras que `true` y `false` no tienen ningún significado especial. Los símbolos que se usan en la directiva `if` se tienen que definir con la línea de comandos o en la configuración del proyecto; no hay ninguna directiva de preprocesador `define`.

El siguiente código muestra el uso de las directivas `#if`, `#else` y `#endif`. En este ejemplo, el código contiene dos versiones de la definición de `function1`. Cuando `VERSION1` se define utilizando el [-define (opción del compilador)](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04), el código entre la `#if` directiva y la `#else` se activa la directiva. De lo contrario, se activará el código entre `#else` y `#endif`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

No hay ninguna directiva de preprocesador `#define` en F#. Hay que usar la configuración del proyecto o la opción del compilador pertinente para definir los símbolos que la directiva `#if` usa.

Las directivas de compilación condicional se pueden anidar. La sangría no es significativa en las directivas de preprocesador.

También puede invalidar un símbolo con `!`. En este ejemplo, un valor de cadena es algo sólo cuando _no_ depuración:

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a>Directivas de línea

Al compilar, el compilador informa de los posibles errores en el código de F# haciendo referencia a los números de línea en los que cada error se produce. Estos números de línea empiezan por 1 en la primera línea en un archivo. Pero si genera código fuente de F# con otra herramienta, los números de línea en el código generado no suelen ser de interés, ya que lo más probable es que los errores en el código de F# generado provengan de otro código fuente. La directiva `#line` constituye una forma de que los creadores de herramientas que generan código fuente de F# pasen información sobre los archivos de origen y los números de línea originales al código de F# generado.

Cuando se usa la directiva `#line`, es necesario que los nombres de archivo estén entre comillas. A menos que el token textual (`@`) aparezca delante de la cadena, hay que anteponer caracteres de barra diagonal inversa usando dos caracteres de barra diagonal inversa en lugar de uno, ya que así se podrán usar en la ruta de acceso. Los siguientes tokens de línea son válidos. En estos ejemplos, se da por hecho que el archivo original `Script1` da como resultado un archivo de código de F# generado automáticamente cuando se ejecuta con una herramienta y, asimismo, que el código en la ubicación de estas directivas se genera a partir de determinados tokens en la línea 25 del archivo `Script1`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

Estos tokens indican que el código de F# generado en esta ubicación se deriva de algunas construcciones en la línea `25` en `Script1`, o cerca de ella.

## <a name="compiler-directives"></a>Directivas de compilador

Las directivas de compilador se parecen a las directivas de preprocesador porque llevan como prefijo un signo #, pero el preprocesador no las interpreta, sino que se dejan para que el compilador las interprete y actúe en consecuencia.

En la siguiente tabla se recoge una lista de las directivas de compilador disponibles en F#.

|Directiva|Descripción|
|---------|-----------|
|`#light` ["activado"&#124;"desactivado"]|Habilita o deshabilita la sintaxis ligera de cara a la compatibilidad con otras versiones de ML. La sintaxis ligera está habilitada de forma predeterminada. La sintaxis detallada siempre está habilitada. Por lo tanto, puede usar ambas sintaxis, la ligera y la detallada. La directiva `#light` es equivalente en sí misma a `#light "on"`. Si especifica `#light "off"`, tendrá que usar la sintaxis detallada en todas las construcciones del lenguaje. La sintaxis en la documentación de F# se muestra bajo la asunción de que se está usando la sintaxis ligera. Para obtener más información, consulte [sintaxis detallada](verbose-syntax.md).|

Las directivas de intérprete (fsi.exe), consulte [programación interactiva con F# ](../tutorials/fsharp-interactive/index.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Opciones del compilador](compiler-options.md)