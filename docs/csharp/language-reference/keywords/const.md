---
title: 'Palabra clave const: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 812aeb331b6dd333075d19076a896246ecc5b374
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713676"
---
# <a name="const-c-reference"></a>const (Referencia de C#)

La palabra clave `const` se usa para declarar un campo constante o una local constante. Los campos y locales constantes no son variables y no se pueden modificar. Las constantes pueden ser números, valores booleanos, cadenas o una referencia nula. No cree una constante para representar información que espera que cambie en algún momento. Por ejemplo, no use un campo constante para almacenar el precio de un servicio, un número de versión de producto o el nombre comercial de una compañía. Estos valores pueden cambiar con el tiempo y, como los compiladores propagan las constantes, otro código compilado con sus bibliotecas tendrán que volver a compilarse para ver los cambios. Vea también la palabra clave [readonly](./readonly.md). Por ejemplo:

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a>Comentarios

El tipo de una declaración constante especifica el tipo de los miembros que la declaración presenta. El inicializador de una local constante o de un campo constante debe ser una expresión constante que se pueda convertir implícitamente al tipo de destino.

Una expresión constante es una expresión que se puede evaluar por completo en tiempo de compilación. Por lo tanto, los únicos valores posibles para las constantes de tipos de referencia son `string` y una referencia nula.

La declaración de constante puede declarar varias constantes, tales como:

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

El modificador `static` no se permite en una declaración de constante.

Una constante puede participar en una expresión constante, de la siguiente manera:

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> La palabra clave [readonly](./readonly.md) difiere de la palabra clave `const`. Un campo `const` solo se puede inicializar en la declaración del campo. Un campo `readonly` se puede inicializar en la declaración o en un constructor. Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use. Además, aunque un campo `const` es una constante en tiempo de compilación, el campo `readonly` se puede usar para constantes en tiempo de ejecución, como en esta línea: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`

## <a name="example"></a>Ejemplo

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a>Ejemplo

Este ejemplo demuestra cómo usar las constantes como variables locales.

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](./index.md)
- [Modificadores](index.md)
- [readonly](./readonly.md)
