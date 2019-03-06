---
title: 'Funciones anónimas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymous functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: f7ab471514cd437b7b1816d7e0bde30459f281a9
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203329"
---
# <a name="anonymous-functions-c-programming-guide"></a>Funciones anónimas (Guía de programación de C#)
Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado. Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.  
  
 Hay dos tipos de funciones anónimas, que se describen por separado en los temas siguientes:  
  
-   [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Las expresiones lambda se pueden enlazar a árboles de expresión y también a delegados.  
  
## <a name="the-evolution-of-delegates-in-c"></a>La evolución de los delegados en C\#
 En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código. C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado. C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas. Estas dos características se conocen colectivamente como *funciones anónimas*. En general, las aplicaciones destinadas a la versión 3.5 y posteriores de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] deberían usar expresiones lambda.  
  
 En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#65)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
- [Árboles de expresión (C#)](../concepts/expression-trees/index.md)
