---
title: 'Excepciones generadas por el compilador: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 2a6b2c3fa053f1c555856df8098975340e78e2b2
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705319"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Excepciones generadas por el compilador (Guía de programación de C#)
Algunas excepciones las inicia automáticamente el entorno Common Language Runtime (CLR) de .NET Framework cuando se producen errores de operaciones básicas. En la tabla siguiente se enumeran estas excepciones y sus condiciones de error.  
  
|Excepción|Descripción|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|Una clase base para las excepciones que se producen durante las operaciones aritméticas, como <xref:System.DivideByZeroException> y <xref:System.OverflowException>.|  
|<xref:System.ArrayTypeMismatchException>|Se inicia cuando una matriz no puede almacenar un elemento determinado porque el tipo real del elemento es incompatible con el tipo real de la matriz.|  
|<xref:System.DivideByZeroException>|Se inicia cuando se intenta dividir un valor entero entre cero.|  
|<xref:System.IndexOutOfRangeException>|Se inicia cuando se intenta indexar una matriz y el índice es menor que cero o queda fuera de los límites de la matriz.|  
|<xref:System.InvalidCastException>|Se inicia cuando se produce un error en una conversión explícita de un tipo base en una interfaz o un tipo derivado en tiempo de ejecución.|  
|<xref:System.NullReferenceException>|Se inicia cuando se intenta hacer referencia a un objeto cuyo valor es [null](../../language-reference/keywords/null.md).|  
|<xref:System.OutOfMemoryException>|Se inicia cuando se produce un error al intentar asignar memoria con el operador [new](../../language-reference/operators/new-operator.md). Indica que se ha agotado la memoria disponible para el entorno Common Language Runtime.|  
|<xref:System.OverflowException>|Se inicia cuando se desborda una operación aritmética en un contexto `checked`.|  
|<xref:System.StackOverflowException>|Se inicia cuando se agota la pila de ejecución por tener demasiadas llamadas a métodos pendientes. Normalmente, indica una recursividad muy profunda o infinita.|  
|<xref:System.TypeInitializationException>|Se inicia cuando un constructor estático inicia una excepción y no existe una cláusula `catch` compatible para capturarla.|  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Excepciones y control de excepciones](./index.md)
- [Control de excepciones](./exception-handling.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
