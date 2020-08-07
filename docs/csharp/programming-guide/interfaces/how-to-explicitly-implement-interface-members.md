---
title: 'Procedimiento Implementar explícitamente miembros de interfaz: Guía de programación de C#'
description: Aprenda a implementar explícitamente miembros de interfaz en este ejemplo de C#. Se accede a los miembros mediante la instancia de interfaz.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303080"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Procedimiento Implementar explícitamente miembros de interfaz (Guía de programación de C#)
Este ejemplo declara una [interfaz](../../language-reference/keywords/interface.md), `IDimensions`, y una clase, `Box`, que implementa explícitamente los miembros de interfaz `GetLength` y `GetWidth`. Se tiene acceso a los miembros mediante la instancia de interfaz `dimensions`.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Programación sólida  
  
- Tenga en cuenta que las siguientes líneas, en el método `Main`, se comentan porque producirían errores de compilación. No se puede tener acceso a un miembro de interfaz que se implementa explícitamente desde una instancia [class](../../language-reference/keywords/class.md):  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Tenga en cuenta también que las líneas siguientes, en el método `Main`, imprimen correctamente las dimensiones del cuadro porque se llama a los métodos desde una instancia de la interfaz:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Clases y structs](../classes-and-structs/index.md)
- [Interfaces](./index.md)
- [Procedimiento para implementar miembros de dos interfaces de forma explícita](./how-to-explicitly-implement-members-of-two-interfaces.md)
