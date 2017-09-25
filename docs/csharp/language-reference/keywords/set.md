---
title: set (Referencia de C#)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- set
- set_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: de10e3978d768aab34efa675fe00cfd059ff55df
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="set-c-reference"></a>set (Referencia de C#)
La palabra clave `set` define un método de *descriptor de acceso* en una propiedad o indexador que asigna el valor de la propiedad o del elemento del indexador. Para obtener más información y ejemplos, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../../csharp/programming-guide/indexers/index.md).  
  
En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`. Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.  
 
 [!code-cs[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  

A menudo, el descriptor de acceso `set` consta de una única instrucción que devuelve un valor, como en el ejemplo anterior. A partir de C# 7, se puede implementar el descriptor de acceso `set` como un miembro con forma de expresión. En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.

 [!code-cs[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
    
En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente. En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente. 
  
 [!code-cs[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
    
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)

