---
title: 'Funciones locales: Guía de programación de C#'
ms.date: 06/14/2017
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: 2036e576a44aa3e1e7829e2091e5a9243d6b6010
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705527"
---
# <a name="local-functions-c-programming-guide"></a>Funciones locales (Guía de programación de C#)

A partir de C# 7.0, C# admite *funciones locales*. Las funciones locales son métodos privados de un tipo que están anidados en otro miembro. Solo se pueden llamar desde su miembro contenedor. Las funciones locales se pueden declarar en y llamar desde:

- Métodos, especialmente los métodos de iterador y asincrónicos
- Constructores
- Descriptores de acceso de propiedad
- Descriptores de acceso de un evento
- Métodos anónimos
- Expresiones lambda
- Finalizadores
- Otras funciones locales

En cambio, las funciones locales no se pueden declarar dentro de un miembro con forma de expresión.

> [!NOTE]
> En algunos casos, puede usar una expresión lambda para implementar funcionalidad compatible también con una función local. Para ver una comparación, consulte [Funciones locales frente a expresiones lambda](../../local-functions-vs-lambdas.md).

Las funciones locales aclaran la intención del código. Cualquiera que lea el código puede ver que solo el método que lo contiene puede llamar al método. Para los proyectos de equipo, también hacen que sea imposible que otro desarrollador llame erróneamente al método de forma directa desde cualquier otro punto de la clase o estructura.
 
## <a name="local-function-syntax"></a>Sintaxis de función local

Una función local se define como un método anidado dentro de un miembro contenedor. Su definición tiene la siguiente sintaxis:

```csharp
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

Las funciones locales pueden usar los modificadores [async](../../language-reference/keywords/async.md) y [unsafe](../../language-reference/keywords/unsafe.md). 

Tenga en cuenta que todas las variables locales que se definen en el miembro contenedor, incluidos sus parámetros de método, son accesibles en la función local. 

A diferencia de una definición de método, una definición de función local no puede incluir el modificador de acceso de los miembros. Dado que todas las funciones locales son privadas, incluido un modificador de acceso, como la palabra clave `private`, se genera el error del compilador CS0106, "El modificador 'private' no es válido para este elemento".

> [!NOTE]
> En las versiones anteriores a C# 8.0, las funciones locales no podían incluir el modificador `static`. Al incluir la palabra clave `static`, se genera el error del compilador CS0106, "El modificador 'static' no es válido para este elemento".

Además, los atributos no se pueden aplicar a la función local o a sus parámetros y parámetros de tipo. 
 
En el ejemplo siguiente, se define una función local denominada `AppendPathSeparator` que es privada a un método denominado `GetText`:
   
[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a>Excepciones y funciones locales

Una de las características útiles de las funciones locales es que pueden permitir que las excepciones aparezcan inmediatamente. Para los iteradores de método, las excepciones aparecen solo cuando la secuencia devuelta se enumera y no cuando se recupera el iterador. Para los métodos asincrónicos, las excepciones producidas en un método asincrónico se observan cuando se espera la tarea devuelta. 

En el ejemplo siguiente, se define un método `OddSequence` que enumera los números impares entre un intervalo especificado. Dado que pasa un número mayor de 100 al método de enumerador `OddSequence`, el método produce una excepción <xref:System.ArgumentOutOfRangeException>. Como se muestra en el resultado del ejemplo, la excepción aparece solo cuando itera los números, y no al recuperar el enumerador.

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

En su lugar, puede producir una excepción al realizar la validación y antes de recuperar el iterador al devolver el iterador de una función local, como se muestra en el ejemplo siguiente.

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

Las funciones locales se pueden usar de forma similar, para controlar las excepciones fuera de la operación asincrónica. Normalmente, las excepciones producidas en el método asincrónico requieren que examine las excepciones internas de una excepción <xref:System.AggregateException>. Las funciones locales permiten que el código genere un error inmediato y permiten que la excepción se produzca y observe de forma sincrónica.

En el ejemplo siguiente, se usa un método asincrónico denominado `GetMultipleAsync` para pausar durante un número especificado de segundos y se devuelve un valor que es un múltiplo aleatorio de ese número de segundos. El retraso máximo es de 5 segundos; se produce una excepción <xref:System.ArgumentOutOfRangeException> si el valor es mayor que 5. Como se muestra en el ejemplo siguiente, la excepción que produce cuando se pasa un valor de 6 al método `GetMultipleAsync` se encapsula en una excepción <xref:System.AggregateException> después de que el método `GetMultipleAsync` empiece a ejecutarse.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

Igual que hemos hecho con el iterador de método, podemos refactorizar el código de este ejemplo para realizar la validación antes de llamar al método asincrónico. Como se muestra en el resultado del ejemplo siguiente, la excepción <xref:System.ArgumentOutOfRangeException> no se encapsula en una excepción <xref:System.AggregateException>.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a>Vea también

- [Métodos](methods.md)
