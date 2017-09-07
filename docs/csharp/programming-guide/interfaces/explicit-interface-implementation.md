---
title: "Implementación de interfaz explícita (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
caps.latest.revision: 14
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
ms.openlocfilehash: 6baf985e8031e1e859d20570168222ca8f368eff
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementación de interfaz explícita (Guía de programación de C#)
Si una [clase](../../../csharp/language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación. En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.  
  
 [!code-cs[csProgGuideInheritance#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_1.cs)]  
  
 En cambio, si los dos miembros de [interfaz](../../../csharp/language-reference/keywords/interface.md) no realizan la misma función, esto puede provocar una implementación incorrecta de una o ambas interfaces. Es posible implementar un miembro de interfaz explícitamente, mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz. Esto se consigue asignando un nombre al miembro de clase con el nombre de la interfaz y un período. Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_2.cs)]  
  
 El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`. Ambas implementaciones de método son independientes, y ninguna está disponible directamente en la clase. Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_3.cs)]  
  
 La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método:  
  
 [!code-cs[csProgGuideInheritance#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_4.cs)]  
  
 Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad P, o el método P o ambos, para evitar un error del compilador. Por ejemplo:  
  
 [!code-cs[csProgGuideInheritance#43](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/explicit-interface-implementation_5.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Interfaces](../../../csharp/programming-guide/interfaces/index.md)   
 [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

