---
title: 'Procedimiento Implementar explícitamente miembros de interfaz: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5ef8b42fe5ca07548d52b88720ea4845d2408bb1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589207"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="8a03f-102">Procedimiento Implementar explícitamente miembros de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8a03f-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="8a03f-103">Este ejemplo declara una [interfaz](../../language-reference/keywords/interface.md), `IDimensions`, y una clase, `Box`, que implementa explícitamente los miembros de interfaz `getLength` y `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="8a03f-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="8a03f-104">Se tiene acceso a los miembros mediante la instancia de interfaz `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="8a03f-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a03f-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a03f-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8a03f-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8a03f-106">Robust Programming</span></span>  
  
- <span data-ttu-id="8a03f-107">Tenga en cuenta que las siguientes líneas, en el método `Main`, se comentan porque producirían errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="8a03f-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="8a03f-108">No se puede tener acceso a un miembro de interfaz que se implementa explícitamente desde una instancia [class](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="8a03f-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="8a03f-109">Tenga en cuenta también que las líneas siguientes, en el método `Main`, imprimen correctamente las dimensiones del cuadro porque se llama a los métodos desde una instancia de la interfaz:</span><span class="sxs-lookup"><span data-stu-id="8a03f-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="8a03f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a03f-110">See also</span></span>

- [<span data-ttu-id="8a03f-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8a03f-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8a03f-112">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="8a03f-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="8a03f-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="8a03f-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="8a03f-114">Cómo: Implementar explícitamente miembros de dos interfaces</span><span class="sxs-lookup"><span data-stu-id="8a03f-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
