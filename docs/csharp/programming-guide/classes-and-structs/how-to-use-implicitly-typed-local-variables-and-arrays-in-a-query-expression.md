---
title: Procedimiento para usar matrices y variables locales con tipo implícito en expresiones de consulta - Guía de programación de C#
description: Use variables locales con tipo implícito en C# para hacer que el compilador determine el tipo de una variable local. Tendrá que usarlas para almacenar tipos anónimos.
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
ms.openlocfilehash: 0379cf7a172b989a9c686fd2da20ca8bf8da4997
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "95098870"
---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a>Procedimiento para usar matrices y variables locales con tipo implícito en expresiones de consulta (Guía de programación de C#)

Puede usar variables locales con tipo implícito siempre que quiera que el compilador determine el tipo de una variable local. Debe usar variables locales con tipo implícito para almacenar tipos anónimos, que a menudo se usan en las expresiones de consulta. En los ejemplos siguientes, se muestran los usos obligatorios y opcionales de las variables locales con tipo implícito en las consultas.  
  
 Las variables locales con tipo implícito se declaran mediante la palabra clave contextual [var](../../language-reference/keywords/var.md). Para obtener más información, vea [Variables locales con asignación implícita de tipos](./implicitly-typed-local-variables.md) y [Matrices con asignación implícita de tipos](../arrays/implicitly-typed-arrays.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, se muestra un escenario común en el que la palabra clave `var` es necesaria: una expresión de consulta que genera una secuencia de tipos anónimos. En este escenario, la variable de consulta y la variable de iteración en la instrucción `foreach` deben escribirse de forma implícita mediante el uso de `var` porque no se tiene acceso a un nombre de tipo para el tipo anónimo. Para obtener más información sobre los tipos anónimos, vea [Tipos anónimos](./anonymous-types.md).  
  
 [!code-csharp[csProgGuideLINQ#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#32)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, se usa la palabra clave `var` en una situación similar, pero en la que el uso de `var` es opcional. Dado que `student.LastName` es una cadena, la ejecución de la consulta devuelve una secuencia de cadenas. Por tanto, el tipo de `queryID` podría declararse como `System.Collections.Generic.IEnumerable<string>` en lugar de `var`. La palabra clave `var` se usa por comodidad. En el ejemplo, la variable de iteración en la instrucción `foreach` se escribe de forma explícita como una cadena, pero se podría declarar mediante `var`. Dado que el tipo de la variable de iteración no es un tipo anónimo, el uso de `var` es opcional, no es obligatorio. Recuerde que `var` no es un tipo, sino una instrucción para que el compilador deduzca y asigne el tipo.  
  
 [!code-csharp[csProgGuideLINQ#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#33)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Métodos de extensión](./extension-methods.md)
- [LINQ (Language Integrated Query)](../../linq/index.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ en C#](../../linq/index.md)
