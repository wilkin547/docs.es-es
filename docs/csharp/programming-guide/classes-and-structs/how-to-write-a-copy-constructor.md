---
title: "Cómo: Escribir un constructor Copy (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
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
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: 1f137b21ff66a2acb58427ccd234c48e2d1b9aff
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Cómo: Escribir un constructor Copy (Guía de programación de C#)
C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `Person`[class](../../../csharp/language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`. Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`. El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.  
  
 [!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ICloneable>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md)  (Constructores [Guía de programación de C#])  
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)
