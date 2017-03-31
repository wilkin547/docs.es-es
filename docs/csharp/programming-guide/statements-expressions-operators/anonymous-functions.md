---
title: "Funciones anónimas (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 465097f9e7024ecfa96ecacb3f4377f3e6a44d13
ms.lasthandoff: 03/13/2017

---
# <a name="anonymous-functions-c-programming-guide"></a>Funciones anónimas (Guía de programación de C#)
Una función anónima es una instrucción o expresión "alineada" que se puede usar siempre que se espera un tipo delegado. Se puede usar para inicializar un delegado con nombre o se puede pasar como un parámetro de método en lugar de un tipo delegado con nombre.  
  
 Hay dos tipos de funciones anónimas, que se describen por separado en los temas siguientes:  
  
-   [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Las expresiones lambda se pueden enlazar a árboles de expresión y también a delegados.  
  
## <a name="the-evolution-of-delegates-in-c"></a>La evolución de los delegados en C#  
 En C# 1.0, una instancia de un delegado se creaba al inicializarla de forma explícita con un método que se definía en otro lugar en el código. C# 2.0 introdujo el concepto de métodos anónimos como una manera de escribir bloques de instrucciones insertados sin nombre que se podían ejecutar en la invocación de un delegado. C# 3.0 introdujo las expresiones lambda, que son similares en concepto a los métodos anónimos, pero más expresivas y concisas. Estas dos características se conocen colectivamente como *funciones anónimas*. En general, las aplicaciones destinadas a la versión 3.5 y posteriores de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] deberían usar expresiones lambda.  
  
 En el ejemplo siguiente se muestra la evolución de la creación de delegados desde C# 1.0 a C# 3.0:  
  
 [!code-cs[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones, expresiones y operadores](../../../csharp/programming-guide/statements-expressions-operators/index.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)
