---
title: 'Excepciones y control de excepciones: Guía de programación de C#'
description: Obtenga más información sobre las excepciones y cómo controlarlas. Estas características de C# ayudan a lidiar con aquellas situaciones excepcionales o inesperadas que se dan cuando un programa se está ejecutando.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
ms.openlocfilehash: 679171e6d397741ef44cb37fb770f6feba039fd9
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110629"
---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Excepciones y control de excepciones (Guía de programación de C#)

Las características de control de excepciones del lenguaje C# le ayudan a afrontar cualquier situación inesperada o excepcional que se produce cuando se ejecuta un programa. El control de excepciones usa las palabras clave `try`, `catch` y `finally` para intentar realizar acciones que pueden no completarse correctamente, para controlar errores cuando decide que es razonable hacerlo y para limpiar recursos más adelante. Las excepciones las puede generar Common Language Runtime (CLR), .NET, bibliotecas de terceros o el código de aplicación. Las excepciones se crean mediante el uso de la palabra clave `throw`.

En muchos casos, una excepción la puede no producir un método al que el código ha llamado directamente, sino otro método más bajo en la pila de llamadas. Cuando se genera una excepción, CLR desenreda la pila, busca un método con un bloque `catch` para el tipo de excepción específico y ejecuta el primer bloque `catch` que encuentra. Si no encuentra ningún bloque `catch` adecuado en cualquier parte de la pila de llamadas, finalizará el proceso y mostrará un mensaje al usuario.

En este ejemplo, un método prueba a hacer la división entre cero y detecta el error. Sin el control de excepciones, este programa finalizaría con un error **DivideByZeroException no controlada**.

:::code language="csharp" source="snippets/exceptions/ExceptionTest.cs" ID="ExceptionTest":::

## <a name="exceptions-overview"></a>Información general sobre excepciones

Las excepciones tienen las siguientes propiedades:

- Las excepciones son tipos que derivan en última instancia de `System.Exception`.
- Use un bloque `try` alrededor de las instrucciones que pueden producir excepciones.
- Una vez que se produce una excepción en el bloque `try`, el flujo de control salta al primer controlador de excepciones asociado que está presente en cualquier parte de la pila de llamadas. En C#, la palabra clave `catch` se utiliza para definir un controlador de excepciones.
- Si no hay ningún controlador de excepciones para una excepción determinada, el programa deja de ejecutarse con un mensaje de error.
- No detecte una excepción a menos que pueda controlarla y dejar la aplicación en un estado conocido. Si se detecta `System.Exception`, reinícielo con la palabra clave `throw` al final del bloque `catch`.
- Si un bloque `catch` define una variable de excepción, puede utilizarla para obtener más información sobre el tipo de excepción que se ha producido.
- Las excepciones puede generarlas explícitamente un programa con la palabra clave `throw`.
- Los objetos de excepción contienen información detallada sobre el error, como el estado de la pila de llamadas y una descripción de texto del error.
- El código de un bloque `finally` se ejecuta incluso si se produce una excepción. Use un bloque `finally` para liberar recursos, por ejemplo, para cerrar las secuencias o los archivos que se abrieron en el bloque `try`.
- Las excepciones administradas de .NET se implementan en el mecanismo de control de excepciones estructurado de Win32. Para más información, vea [Control de excepciones estructurado (C/C++)](/cpp/cpp/structured-exception-handling-c-cpp) y [A Crash Course on the Depths of Win32 Structured Exception Handling](http://bytepointer.com/resources/pietrek_crash_course_depths_of_win32_seh.htm) (Curso intensivo sobre los aspectos específicos del control de excepciones estructurado de Win32).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, consulte la sección [Excepciones](~/_csharplang/spec/exceptions.md) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.SystemException>
- [Palabras clave de C#](../../language-reference/keywords/index.md)
- [throw](../../language-reference/keywords/throw.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Excepciones](../../../standard/exceptions/index.md)
