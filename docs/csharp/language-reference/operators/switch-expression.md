---
title: 'Expresión switch: referencia de C#'
description: Obtenga información sobre cómo usar la expresión switch de C# para la coincidencia de patrones y otra introspección de datos
ms.date: 03/19/2020
ms.openlocfilehash: 9e609bcea0f92f492b5f9b07840e47f75c1b71e4
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249763"
---
# <a name="switch-expression-c-reference"></a>Expresión switch (referencia de C#)

En este artículo se trata la expresión `switch`, introducida en C# 8.0. Para obtener información sobre la instrucción `switch`, consulte el artículo sobre la [instrucción `switch`](../keywords/switch.md) en la sección [Instrucciones](../keywords/index.md).

## <a name="basic-example"></a>Ejemplo básico

La expresión `switch` se proporciona para una semántica similar a `switch` en un contexto de expresión. Proporciona una sintaxis concisa cuando los segmentos modificadores producen un valor. En el ejemplo siguiente se muestra la estructura de una expresión switch. Traslada los valores desde una `enum` que representa las direcciones visuales de un mapa en línea hasta la dirección cardinal correspondiente:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetBasicStructure":::

En el ejemplo anterior se muestran los elementos básicos de una expresión switch:

- La *expresión de intervalo*: En el ejemplo anterior se usa la variable `direction` como expresión de intervalo.
- Los *segmentos de expresión switch*: Cada segmento de expresión switch contiene un *patrón*, una *restricción de caso*, el token `=>` y una *expressión*.

El resultado de la *expresión switch* es el valor de la expresión del primer *segmento de expresión switch* cuyo *patrón* coincide con la *expresión de intervalo* y cuya *restricción de caso*, en caso de estar presente, se evalúa como `true`. La *expresión* situada a la derecha del token `=>` no puede ser una instrucción de expresión.

Los *segmentos de expresión switch* se evalúan en orden de texto. El compilador emite un error cuando no se puede elegir un *segmento de expresión switch* inferior porque un *segmento de expresión switch* superior coincide con todos sus valores.

## <a name="patterns-and-case-guards"></a>Patrones y restricciones de caso

Muchos patrones se admiten en los segmentos de expresión switch. En el ejemplo anterior se usó en *patrón de valor*. Un *patrón de valor* compara la expresión de intervalo con un valor. Ese valor debe ser una constante de tiempo de compilación. El *patrón de valor* compara la expresión de intervalo con un tipo conocido. En el siguiente ejemplo se recupera el tercer elemento de una secuencia. Usa distintos métodos en función del tipo de la secuencia:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetTypePattern":::

Los patrones pueden ser recursivos, donde un patrón prueba un tipo, y si ese tipo coincide, el patrón coincide con uno o varios valores de propiedad en la expresión de intervalo. Puede usar patrones recursivos para ampliar el ejemplo anterior. Agregue segmentos de expresión switch para matrices que tengan menos de tres elementos. Los patrones recursivos se muestran en el ejemplo siguiente:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetRecursivePattern":::

Los patrones recursivos pueden examinar las propiedades de la expresión de intervalo, pero no pueden ejecutar código arbitrario. Puede usar una *restricción de caso*, especificada en una cláusula `when`, para proporcionar comprobaciones similares para otros tipos de secuencia:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetGuardCase":::

Por último, puede agregar los patrones `_` y `null` para detectar argumentos no procesados por ningún otro segmento de expresión switch. Eso hace que la expresión switch sea *exhaustiva*, lo que significa que se controla cualquier valor posible de la expresión de intervalo. En el siguiente ejemplo se agregan esos segmentos de expresión:

:::code language="csharp" source="snippets/SwitchExpressions.cs" id="SnippetExhaustive":::

En el ejemplo anterior se agrega un patrón `null` y se cambia el patrón de tipo `IEnumerable<T>` a un patrón `_`. El patrón `null` proporciona una comprobación de NULL como segmento de expresión switch. La expresión para ese segmento inicia una excepción <xref:System.ArgumentNullException>. El patrón `_` coincide con todas las entradas que no han coincidido con segmentos anteriores. Debe aparecer después de la comprobación `null` o coincidiría con las entradas `null`.

Puede leer más en la propuesta de especificación de lenguaje C# para [patrones recursivos](~/_csharplang/proposals/csharp-8.0/patterns.md#switch-expression).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- [Coincidencia de patrones](../../pattern-matching.md)
