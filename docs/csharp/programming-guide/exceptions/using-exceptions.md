---
title: 'Usar excepciones: Guía de programación de C#'
description: Aprenda a usar excepciones. Las excepciones las inicia el código que encuentra un error y las detecta el código que lo corrige.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], about exceptions
ms.assetid: 71472c62-320a-470a-97d2-67995180389d
ms.openlocfilehash: 30a7c3eecb599493dfa74d664c4899836c1b9276
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110226"
---
# <a name="use-exceptions-c-programming-guide"></a>Uso de excepciones (guía de programación de C#)

En C#, los errores del programa en tiempo de ejecución se propagan a través del programa mediante un mecanismo denominado excepciones. Las excepciones las inicia el código que encuentra un error y las detecta el código que puede corregir dicho error. El entorno de ejecución .NET o el código de un programa pueden producir excepciones. Una vez iniciada, una excepción se propaga hasta la pila de llamadas hasta que encuentra una instrucción `catch` para la excepción. Las excepciones no detectadas se controlan mediante un controlador de excepciones que ofrece el sistema y muestra un cuadro de diálogo.

Las excepciones están representadas por clases derivadas de <xref:System.Exception>. Esta clase identifica el tipo de excepción y contiene propiedades que tienen los detalles sobre la excepción. Iniciar una excepción implica crear una instancia de una clase derivada de excepción, configurar opcionalmente las propiedades de la excepción y luego producir el objeto con la palabra clave `throw`. Por ejemplo:

:::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowException":::

Cuando se inicia una excepción, el entorno runtime comprueba la instrucción actual para ver si se encuentra dentro de un bloque `try`. Si es así, se comprueban los bloques `catch` asociados al bloque `try` para ver si pueden detectar la excepción. Los bloques `Catch` suelen especificar tipos de excepción; si el tipo del bloque `catch` es el mismo de la excepción, o una clase base de la excepción, el bloque `catch` puede controlar el método. Por ejemplo:

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CatchException":::

Si la instrucción que inicia una excepción no está en un bloque `try`, o si el bloque `try` que la encierra no tiene un elemento `catch` coincidente, el entorno de ejecución busca una instrucción `try` y bloques `catch` en el método de llamada. El entorno runtime sigue hasta la pila de llamadas para buscar un bloque `catch` compatible. Después de encontrar el bloque `catch` y ejecutarlo, el control pasa a la siguiente instrucción después de dicho bloque `catch`.

Una instrucción `try` puede contener más de un bloque `catch`. Se ejecuta la primera instrucción `catch` que pueda controlar la excepción; las instrucciones `catch` siguientes se omiten, aunque sean compatibles. Los bloques catch deben ordenarse siempre de más específico (o más derivado) a menos específico. Por ejemplo:

:::code language="csharp" source="snippets/exceptions/CatchOrder.cs":::

Para que el bloque `catch` se ejecute, el entorno runtime busca bloques `finally`. Los bloques `Finally` permiten al programador limpiar cualquier estado ambiguo que pudiera haber quedado tras la anulación de un bloque `try` o liberar los recursos externos (como identificadores de gráficos, conexiones de base de datos o flujos de archivos) sin tener que esperar a que el recolector de elementos no utilizados en el entorno de ejecución finalice los objetos. Por ejemplo:

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TestFinally":::

Si `WriteByte()` ha iniciado una excepción, el código del segundo bloque `try` que intente reabrir el archivo generaría un error si no se llama a `file.Close()`, y el archivo permanecería bloqueado. Como los bloques `finally` se ejecutan aunque se inicie una excepción, el bloque `finally` del ejemplo anterior permite que el archivo se cierre correctamente y ayuda a evitar un error.

Si no se encuentra ningún bloque `catch` compatible en la pila de llamadas después de iniciar una excepción, sucede una de estas tres acciones:

- Si la excepción se encuentra en un finalizador, este se anula y, si procede, se llama al finalizador base.
- Si la pila de llamadas contiene un constructor estático o un inicializador de campo estático, se inicia una excepción <xref:System.TypeInitializationException>, y la excepción original se asigna a la propiedad <xref:System.Exception.InnerException%2A> de la nueva excepción.
- Si se llega al comienzo del subproceso, este finaliza.
