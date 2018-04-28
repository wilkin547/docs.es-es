---
title: 'Excepciones: la expresión try...with (F#)'
description: "Obtenga información acerca de cómo usar la expresión 'try... with' de F # para el control de excepciones."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 06e40b79fc1958918dc0615ce9d1004e0a6e74a5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-trywith-expression"></a>Excepciones: expresión try...with

Este tema se describe la `try...with` expresión, la expresión que se usa para el control de excepciones en el lenguaje F #.


## <a name="syntax"></a>Sintaxis

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>Comentarios
El `try...with` expresión se utiliza para controlar las excepciones en F #. Es similar a la `try...catch` instrucción en C#. En la sintaxis anterior, el código en *expression1* podría generar una excepción. El `try...with` expresión devuelve un valor. Si no se produce ninguna excepción, toda la expresión devuelve el valor de *expression1*. Si se produce una excepción, cada uno de ellos *patrón* se compara a su vez con la excepción y para el primer patrón de búsqueda de coincidencias, la correspondiente *expresión*, que se conoce como el *delcontroladordeexcepciones*, para esa bifurcación se ejecuta y toda la expresión devuelve el valor de la expresión en ese controlador de excepciones. Si ningún modelo coincide, la excepción se propaga la pila de llamadas hasta que encuentra un controlador coincidente. Los tipos de los valores devueltos por cada expresión de los controladores de excepción deben coincidir con el tipo devuelto de la expresión en el `try` bloque.

Con frecuencia, el hecho de que ocurrió un error también significa que no hay ningún valor válido que se pueden devolver en las expresiones de cada controlador de excepciones. Una práctica habitual es que el tipo de la expresión sea un tipo de opción. En el ejemplo de código siguiente se muestra este modelo.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Las excepciones pueden estar excepciones de. NET, o pueden ser excepciones de F #. Puede definir excepciones de F # mediante el `exception` palabra clave.

Puede usar una variedad de modelos para filtrar según el tipo de excepción y otras condiciones; en la tabla siguiente se resumen las opciones.


|Modelo|Descripción|
|-------|-----------|
|:? *tipo de excepción*|Coincide con el tipo de excepción de .NET especificado.|
|:? *tipo de excepción* como *identificador*|Coincide con el tipo de excepción de .NET especificado, pero da un valor con nombre de la excepción.|
|*nombre de la excepción*(*argumentos*)|Coincide con un tipo de excepción de F # y enlaza los argumentos.|
|*identifier*|Coincide con cualquier excepción y enlaza el nombre para el objeto de excepción. ¿Equivalente a **:? System.Exception como *** identificador*|
|*identificador* cuando *condición*|Coincide con cualquier excepción si la condición es true.|

## <a name="examples"></a>Ejemplos
Ejemplos de código siguientes muestran el uso de los distintos patrones de controlador de excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
El `try...with` construcción es una expresión independiente desde el `try...finally` expresión. Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos expresiones.

>[!NOTE] 
Puede usar `try...with` en flujos de trabajo asincrónicos y otras expresiones de cálculo, en el que caso una versión personalizada de la `try...with` se utiliza la expresión. Para obtener más información, consulte [flujos de trabajo asincrónicos](../asynchronous-workflows.md), y [expresiones de cálculo](../computation-expressions.md).


## <a name="see-also"></a>Vea también
[Control de excepciones](index.md)

[Tipos de excepción](exception-types.md)

[Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)
