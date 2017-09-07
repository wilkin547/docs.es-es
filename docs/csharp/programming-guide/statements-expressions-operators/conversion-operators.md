---
title: "Operadores de conversión (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c12fd13d6526d79363f973ce2a944c4823bf4104
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="conversion-operators-c-programming-guide"></a>Operadores de conversión (Guía de programación de C#)
C# permite a los programadores declarar conversiones en clases o structs, de manera que las clases o structs puedan convertirse a o desde otras clases o structs, o tipos básicos. Las conversiones se definen como los operadores y se denominan por el tipo al que se convierten. El tipo del argumento que se va a convertir o el tipo del resultado de la conversión, pero no ambos, debe ser el tipo contenedor.  
  
 [!code-cs[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a>Información general sobre operadores de conversión  
 Los operadores de conversión tienen las propiedades siguientes:  
  
-   Las conversiones declaradas como `implicit` se producen automáticamente cuando se necesita.  
  
-   Las conversiones declaradas como `explicit` necesitan que se llame a una conversión.  
  
-   Todas las conversiones se deben declarar como `static`.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información:  
  
-   [Utilizar operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [Cómo: Implementar conversiones definidas por el usuario entre structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Convert>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384) (Conversiones explícitas encadenadas definidas por el usuario en C#)

