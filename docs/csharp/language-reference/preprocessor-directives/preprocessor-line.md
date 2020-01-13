---
title: '#line: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 79033fa652af62c76d54737fbf0a0b47cf3aae99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712499"
---
# <a name="line-c-reference"></a>#line (Referencia de C#)

`#line` le permite modificar el número de línea del compilador y (opcionalmente) la salida del nombre de archivo de errores y advertencias.

En el siguiente ejemplo, se muestra cómo notificar dos advertencias asociadas con números de línea. La directiva `#line 200` fuerza el número de línea siguiente para que sea 200 (aunque el valor predeterminado es 6) y hasta la siguiente directiva `#line`, el nombre de archivo se notificará como "Especial". La directiva `#line default` devuelve la numeración de líneas a su numeración predeterminada, que cuenta las líneas a las que la directiva anterior ha cambiado el número.

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

La compilación genera el siguiente resultado:

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a>Comentarios

La directiva `#line` podría usarse en un paso intermedio automatizado en el proceso de compilación. Por ejemplo, si se han eliminado las líneas del archivo de código fuente original, pero aún quiere que el compilador genere unos resultados en función de la numeración de líneas original en el archivo, puede quitar las líneas y, después, simular la numeración de líneas original con `#line`.

La directiva `#line hidden` oculta las líneas sucesivas del depurador, de forma que, cuando el desarrollador ejecuta paso a paso el código, cualquier línea entre `#line hidden` y la siguiente directiva `#line` (suponiendo que no sea otra directiva `#line hidden`) se depurará paso a paso por procedimientos. Esta opción también se puede usar para permitir que ASP.NET diferencie entre el código generado por el equipo y el definido por el usuario. Aunque ASP.NET es el consumidor principal de esta característica, es probable que la usen más generadores de código fuente.

Una directiva `#line hidden` no afecta a los nombres de archivo o números de línea en el informe de errores. Es decir, si se produce un error en un bloque oculto, el compilador notificará el nombre de archivo y número de línea reales del error.

La directiva `#line filename` especifica el nombre de archivo que quiere que aparezca en la salida del compilador. De forma predeterminada, se usa el nombre real del archivo de código fuente. El nombre de archivo debe estar entre comillas dobles ("") y debe ir precedido de un número de línea.

Un archivo de código fuente puede tener cualquier número de directivas `#line`.

## <a name="example-1"></a>Ejemplo 1

En el ejemplo siguiente, se muestra cómo el depurador omite las líneas ocultas en el código. Al ejecutar el ejemplo, mostrará tres líneas de texto. En cambio, al establecer un punto de interrupción, como se muestra en el ejemplo, y presionar F10 para recorrer el código, observará que el depurador omite la línea oculta. Tenga también en cuenta que, incluso si configura un punto de interrupción en la línea oculta, el depurador lo omitirá.

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Directivas de preprocesador de C#](./index.md)
