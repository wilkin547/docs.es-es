---
title: 'Excepciones generadas por el compilador: Guía de programación de C#'
description: Aprenda sobre las excepciones generadas por el compilador. Revise una lista de excepciones iniciadas automáticamente y sus condiciones de error.
ms.date: 12/09/2020
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 43bacbb1025bc0af3a5f21979315b3d1b0d61066
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110356"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Excepciones generadas por el compilador (Guía de programación de C#)

Algunas excepciones las inicia automáticamente el entorno de ejecución .NET cuando se producen errores de operaciones básicas. En la tabla siguiente se enumeran estas excepciones y sus condiciones de error.

|Excepción|Descripción|
|---------------|-----------------|
|<xref:System.ArithmeticException>|Una clase base para las excepciones que se producen durante las operaciones aritméticas, como <xref:System.DivideByZeroException> y <xref:System.OverflowException>.|
|<xref:System.ArrayTypeMismatchException>|Se inicia cuando una matriz no puede almacenar un elemento determinado porque el tipo real del elemento es incompatible con el tipo real de la matriz.|
|<xref:System.DivideByZeroException>|Se inicia cuando se intenta dividir un valor entero entre cero.|
|<xref:System.IndexOutOfRangeException>|Se inicia cuando se intenta indexar una matriz y el índice es menor que cero o queda fuera de los límites de la matriz.|
|<xref:System.InvalidCastException>|Se inicia cuando se produce un error en una conversión explícita de un tipo base en una interfaz o un tipo derivado en tiempo de ejecución.|
|<xref:System.NullReferenceException>|Se inicia cuando se intenta hacer referencia a un objeto cuyo valor es [null](../../language-reference/keywords/null.md).|
|<xref:System.OutOfMemoryException>|Se inicia cuando se produce un error al intentar asignar memoria con el operador [new](../../language-reference/operators/new-operator.md). Esta excepción indica que se ha agotado la memoria disponible para el entorno compatible con Common Language Runtime.|
|<xref:System.OverflowException>|Se inicia cuando se desborda una operación aritmética en un contexto `checked`.|
|<xref:System.StackOverflowException>|Se inicia cuando se agota la pila de ejecución por tener demasiadas llamadas a métodos pendientes. Normalmente, indica una recursividad muy profunda o infinita.|
|<xref:System.TypeInitializationException>|Se inicia cuando un constructor estático inicia una excepción y no existe una cláusula `catch` compatible para capturarla.|

## <a name="see-also"></a>Vea también

- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
