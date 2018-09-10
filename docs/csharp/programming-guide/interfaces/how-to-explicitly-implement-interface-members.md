---
title: 'Cómo: Implementar explícitamente miembros de interfaz (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 30ea58b7ef3edd757c450b9fca1cc810ff9d17c1
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861028"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="7ad2e-102">Cómo: Implementar explícitamente miembros de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7ad2e-102">How to: Explicitly Implement Interface Members (C# Programming Guide)</span></span>
<span data-ttu-id="7ad2e-103">Este ejemplo declara una [interfaz](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, y una clase, `Box`, que implementa explícitamente los miembros de interfaz `getLength` y `getWidth`.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-103">This example declares an [interface](../../../csharp/language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `getLength` and `getWidth`.</span></span> <span data-ttu-id="7ad2e-104">Se tiene acceso a los miembros mediante la instancia de interfaz `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ad2e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ad2e-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="7ad2e-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="7ad2e-106">Robust Programming</span></span>  
  
-   <span data-ttu-id="7ad2e-107">Tenga en cuenta que las siguientes líneas, en el método `Main`, se comentan porque producirían errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="7ad2e-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="7ad2e-108">No se puede tener acceso a un miembro de interfaz que se implementa explícitamente desde una instancia [class](../../../csharp/language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="7ad2e-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../../csharp/language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   <span data-ttu-id="7ad2e-109">Tenga en cuenta también que las líneas siguientes, en el método `Main`, imprimen correctamente las dimensiones del cuadro porque se llama a los métodos desde una instancia de la interfaz:</span><span class="sxs-lookup"><span data-stu-id="7ad2e-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7ad2e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ad2e-110">See Also</span></span>

- [<span data-ttu-id="7ad2e-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7ad2e-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7ad2e-112">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="7ad2e-112">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="7ad2e-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="7ad2e-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="7ad2e-114">Cómo: Implementar explícitamente miembros de dos interfaces</span><span class="sxs-lookup"><span data-stu-id="7ad2e-114">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
