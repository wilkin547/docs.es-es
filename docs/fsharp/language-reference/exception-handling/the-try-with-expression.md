---
title: 'Excepciones: Expresión try...with'
description: Aprenda a usar la F# instrucción ' try... with ' expresión para el control de excepciones.
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630249"
---
# <a name="exceptions-the-trywith-expression"></a>Excepciones: Expresión try...with

En este tema se `try...with` describe la expresión, la expresión que se utiliza para el control F# de excepciones en el lenguaje.

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

La `try...with` expresión se utiliza para controlar las excepciones F#en. Es similar a la `try...catch` instrucción de. C# En la sintaxis anterior, el código de *expression1* podría generar una excepción. La `try...with` expresión devuelve un valor. Si no se produce ninguna excepción, toda la expresión devuelve el valor de *expression1*. Si se produce una excepción, cada *patrón* se compara a su vez con la excepción, y para el primer patrón coincidente, se ejecuta la *expresión*correspondiente, conocida como *controlador de excepciones*, para esa bifurcación y la expresión general Devuelve el valor de la expresión en ese controlador de excepciones. Si ningún patrón coincide, la excepción propaga la pila de llamadas hasta que se encuentra un controlador coincidente. Los tipos de los valores devueltos por cada expresión en los controladores de excepciones deben coincidir con el tipo devuelto `try` de la expresión en el bloque.

Con frecuencia, el hecho de que se produzca un error también significa que no hay ningún valor válido que se pueda devolver desde las expresiones de cada controlador de excepciones. Un patrón frecuente es que el tipo de la expresión sea un tipo de opción. En el ejemplo de código siguiente se muestra este patrón.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

Las excepciones pueden ser excepciones de .NET o pueden ser F# excepciones. Puede definir F# excepciones mediante la `exception` palabra clave.

Puede usar diversos patrones para filtrar según el tipo de excepción y otras condiciones; las opciones se resumen en la tabla siguiente.

|Modelo|DESCRIPCIÓN|
|-------|-----------|
|:? *exception-type*|Coincide con el tipo de excepción de .NET especificado.|
|:? *tipo de excepción* como *identificador*|Coincide con el tipo de excepción de .NET especificado, pero asigna a la excepción un valor con nombre.|
|*nombre de excepción* (*argumentos*)|Coincide con F# un tipo de excepción y enlaza los argumentos.|
|*identifier*|Coincide con cualquier excepción y enlaza el nombre al objeto de excepción. Equivalente a **:? System. Exception como**_identificador_|
|*identificador* cuando la *condición*|Coincide con cualquier excepción si la condición es true.|

## <a name="examples"></a>Ejemplos

En los siguientes ejemplos de código se muestra el uso de los distintos patrones de controlador de excepciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> La `try...with` construcción es una expresión independiente de la `try...finally` expresión. Por lo tanto, si el código requiere `with` un bloque y `finally` un bloque, tendrá que anidar las dos expresiones.

> [!NOTE]
> Puede usar `try...with` en flujos de trabajo asincrónicos y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `try...with` de la expresión. Para obtener más información, vea [flujos de trabajo asincrónicos](../asynchronous-workflows.md)y expresiones de [cálculo](../computation-expressions.md).

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: La `try...finally` expresión](the-try-finally-expression.md)
