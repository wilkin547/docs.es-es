---
title: get (Referencia de C#) | Microsoft Docs
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
dev_langs:
- CSharp
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cdd3107a9e23e2f41a412390c8a723d4366e3952
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="get-c-reference"></a>get (Referencia de C#)

La palabra clave `get` define un método de *descriptor de acceso* en una propiedad o un indizador que devuelve el valor de la propiedad o el elemento del indizador. Para obtener más información, consulte [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) (Propiedades), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) (Propiedades implementadas automáticamente) e [Indexers](../../../csharp/programming-guide/indexers/index.md) (Indizadores).  
  
En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`. En él se utiliza un campo privado denominado `_seconds` para respaldar el valor de la propiedad.  
 
 [!code-cs[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
A menudo, el descriptor de acceso `get` consta de una única instrucción que devuelve un valor, como en el ejemplo anterior. A partir de C# 7, se puede implementar el descriptor de acceso `get` como un miembro con forma de expresión. En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.

 [!code-cs[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente. En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente. 
  
 [!code-cs[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [C# Keywords](../../../csharp/language-reference/keywords/index.md)
 [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) (Propiedades de las palabras claves de C#)

