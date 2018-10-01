---
title: Expresiones de valor predeterminado (Guía de programación de C#)
description: Las expresiones de valor predeterminado generan el valor predeterminado de cualquier tipo de referencia o valor.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47192633"
---
# <a name="default-value-expressions-c-programming-guide"></a>Expresiones de valor predeterminado (Guía de programación de C#)

Una expresión de valor predeterminado `default(T)` genera el valor predeterminado de un tipo `T`. La siguiente tabla muestra los valores que se generan para distintos tipos:

|Tipo|Valor predeterminado|
|---------|---------|
|Cualquier tipo de referencia|`null`|
|Tipo de valor numérico|Cero|
|[bool](../../language-reference/keywords/bool.md)|`false`|
|[char](../../language-reference/keywords/char.md)|`'\0'`|
|[enum](../../language-reference/keywords/enum.md)|Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.|
|[struct](../../language-reference/keywords/struct.md)|Valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.|
|Tipo que acepta valores NULL|Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.|

Las expresiones de valor predeterminado son particularmente útiles en clases y métodos genéricos. Un problema que aparece tras usar elementos genéricos es cómo asignar un valor predeterminado a un `T` de tipo parametrizado cuando no conoce la información siguiente de antemano:

- Si `T` es un tipo de referencia o un tipo de valor.
- Si `T` es un tipo de valor, si es un valor numérico o un struct.

 Dada una variable `t` de un `T` de tipo parametrizado, la instrucción `t = null` solo es válida si `T` es un tipo de referencia. La asignación `t = 0` solo funciona para los tipos de valor numérico, pero no para las estructuras. Para resolverlo, use una expresión de valor predeterminado:

```csharp
T t = default(T);
```

La expresión `default(T)` no se limita a métodos y clases genéricas. Las expresiones de valor predeterminado pueden usarse con cualquier tipo administrado. Cualquiera de estas expresiones es válida:

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 El ejemplo siguiente de la clase `GenericList<T>` muestra cómo usar el operador `default(T)` en una clase genérica. Para obtener más información, vea [Introducción a los genéricos](../generics/introduction-to-generics.md).

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Literal e inferencia de tipo predeterminados

A partir de C# 7.1, el literal `default` puede usarse para las expresiones de valor predeterminado cuando el compilador puede deducir el tipo de expresión. El literal `default` genera el mismo valor que el equivalente `default(T)` cuando se deduce el tipo `T`. Esto puede simplificar el código disminuyendo la redundancia al declarar un tipo más de una vez. El literal `default` puede usarse en cualquiera de las ubicaciones siguientes:

- inicializador de variable
- asignación de variables
- Declarar el valor predeterminado de un parámetro opcional
- Proporcionar el valor de un argumento de método de llamada
- Devolver la instrucción (o una expresión de un miembro con cuerpo de expresión)

El ejemplo siguiente muestra varios usos del literal `default` en una expresión de valor predeterminado:

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>  
- [Guía de programación de C#](../index.md)  
- [Genéricos (Guía de programación de C#)](../generics/index.md)  
- [Métodos genéricos](../generics/generic-methods.md)  
- [Elementos genéricos en .NET](~/docs/standard/generics/index.md)  
- [Tabla de valores predeterminados](../../language-reference/keywords/default-values-table.md)
