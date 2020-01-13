---
title: 'Implementación de interfaz explícita: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ac90726fd50f104d1b9251d4f9b097b721ea5e7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701763"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Implementación de interfaz explícita (Guía de programación de C#)
Si una [clase](../../language-reference/keywords/class.md) implementa dos interfaces que contienen un miembro con la misma firma, entonces al implementar ese miembro en la clase ambas interfaces usarán ese miembro como su implementación. En el ejemplo siguiente, todas las llamadas a `Paint` invocan el mismo método.  
  
 [!code-csharp[csProgGuideInheritance#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#39)]  
  
 En cambio, si los dos miembros de [interfaz](../../language-reference/keywords/interface.md) no realizan la misma función, esto puede provocar una implementación incorrecta de una o ambas interfaces. Es posible implementar un miembro de interfaz explícitamente, mediante la creación de un miembro de clase que solo se llama a través de la interfaz, y es específico de esa interfaz. Esto se consigue asignando un nombre al miembro de clase con el nombre de la interfaz y un período. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#40)]  
  
 El miembro de clase `IControl.Paint` solo está disponible a través de la interfaz `IControl`, y `ISurface.Paint` solo está disponible mediante `ISurface`. Ambas implementaciones de método son independientes, y ninguna está disponible directamente en la clase. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#41)]  
  
 La implementación explícita también se usa para resolver casos donde dos interfaces declaran miembros diferentes del mismo nombre como una propiedad y un método:  
  
 [!code-csharp[csProgGuideInheritance#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#42)]  
  
 Para implementar ambas interfaces, una clase tiene que usar la implementación explícita para la propiedad P, o el método P o ambos, para evitar un error del compilador. Por ejemplo:  
  
 [!code-csharp[csProgGuideInheritance#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#43)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](../classes-and-structs/index.md)
- [Interfaces](./index.md)
- [Herencia](../classes-and-structs/inheritance.md)
