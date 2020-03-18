---
title: Controlar y generar excepciones en .NET
ms.date: 06/19/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET], handling
- runtime, exceptions
- filtering exceptions
- errors [.NET], exceptions
- exceptions [.NET], throwing
- exceptions [.NET]
- common language runtime, exceptions
ms.assetid: f99a1d29-a2a8-47af-9707-9909f9010735
ms.openlocfilehash: 8e78b2a8d7a815637e143eeb88bcfb51ded33771
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75741357"
---
# <a name="handling-and-throwing-exceptions-in-net"></a>Controlar y generar excepciones en .NET

Las aplicaciones tienen que ser capaces de controlar de forma coherente los errores que se producen durante la ejecución. .NET proporciona un modelo para notificar errores a las aplicaciones de manera uniforme: las operaciones .NET indican errores iniciando excepciones.

## <a name="exceptions"></a>Excepciones

Una excepción es cualquier condición de error o comportamiento inesperado que encuentra un programa en ejecución. Las excepciones pueden iniciarse debido a un error en el código propio o en el código al que se llama (por ejemplo, una biblioteca compartida), a recursos del sistema operativo no disponibles, a condiciones inesperadas que encuentra el runtime (por ejemplo, imposibilidad de comprobar el código), etc. La aplicación puede recuperarse de algunas de estas condiciones, pero no de todas. Aunque es posible recuperarse de la mayoría de las excepciones que se producen en la aplicación, no ocurre lo mismo con las excepciones de runtime.

En .NET, una excepción es un objeto que hereda de la clase <xref:System.Exception?displayProperty=nameWithType>. Una excepción se inicia desde un área del código en la que ha producido un problema. La excepción se pasa hacia arriba en la pila hasta que la aplicación la controla o el programa finaliza.

## <a name="exceptions-vs-traditional-error-handling-methods"></a>Excepciones vs. métodos tradicionales de control de errores

Tradicionalmente, el modelo de control de errores de un lenguaje se basaba en el modo exclusivo del lenguaje de detectar los errores y buscarles controladores, o bien en el mecanismo de control de errores ofrecido por el sistema operativo. La forma en que .NET implementa el control de excepciones proporciona las siguientes ventajas:

- La administración e iniciación de excepciones funciona de igual modo para los lenguajes de programación. NET.

- No requiere ninguna sintaxis de lenguaje específica para controlar las excepciones, pero permite que cada lenguaje defina su propia sintaxis.

- Las excepciones pueden iniciarse en varios procesos en incluso límites de máquina.

- Se puede agregar el código de control de excepciones a una aplicación para aumentar la confiabilidad del programa.

Las excepciones ofrecen ventajas sobre otros métodos de notificación de errores, por ejemplo, los códigos de retorno. Lo errores no pasan desapercibidos porque si se inicia una excepción y no la controla, el runtime finaliza la aplicación. Los valores no válidos no continúan propagándose por el sistema como resultado de que el código no pueda encontrar un código de retorno de error.

## <a name="common-exceptions"></a>Excepciones comunes

En la tabla siguiente se muestra algunas excepciones comunes con ejemplos de las causas que las originan.

| Tipo de excepción | Description | Ejemplo |
| -------------- | ----------- | ------- |
| <xref:System.Exception> | Clase base de todas las excepciones. | Ninguno (utilice una clase derivada de esta excepción). |
| <xref:System.IndexOutOfRangeException> | El tiempo de ejecución la genera solo cuando una matriz no está correctamente indexada. | La indexación de una matriz fuera de su intervalo válido: <br /> `arr[arr.Length+1]` |
| <xref:System.NullReferenceException> | El tiempo de ejecución la genera solo cuando se hace referencia a un objeto null. | `object o = null;` <br /> `o.ToString();` |
| <xref:System.InvalidOperationException> | Los métodos la generan si se produce un estado no válido. | Llamada a `Enumerator.MoveNext()` después de quitar un elemento de la colección subyacente. |
| <xref:System.ArgumentException> | Clase base de todas las excepciones de argumento. | Ninguno (utilice una clase derivada de esta excepción). |
| <xref:System.ArgumentNullException> | Los métodos que no permiten que un argumento sea null la generan. | `String s = null;` <br /> `"Calculate".IndexOf(s);`|
| <xref:System.ArgumentOutOfRangeException> | Los métodos que comprueban que los argumentos se encuentran en un intervalo determinado la generan. | `String s = "string";` <br /> `s.Substring(s.Length+1);` |

## <a name="see-also"></a>Vea también

- [Clase Exception y propiedades](exception-class-and-properties.md)
- [Utilizar el bloque Try/Catch para detectar excepciones](how-to-use-the-try-catch-block-to-catch-exceptions.md)
- [Cómo: Utilizar excepciones específicas en un bloque Catch](how-to-use-specific-exceptions-in-a-catch-block.md)
- [Cómo: Iniciar excepciones explícitamente](how-to-explicitly-throw-exceptions.md)
- [Cómo crear excepciones definidas por el usuario](how-to-create-user-defined-exceptions.md)
- [Utilizar controladores de excepciones filtradas por el usuario](using-user-filtered-exception-handlers.md)
- [Utilizar bloques Finally](how-to-use-finally-blocks.md)
- [Controlar excepciones de interoperabilidad COM](handling-com-interop-exceptions.md)
- [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md)
- [¿Qué necesitan saber todos los desarrolladores acerca de las excepciones producidas en el runtime?](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/exceptions.md)
