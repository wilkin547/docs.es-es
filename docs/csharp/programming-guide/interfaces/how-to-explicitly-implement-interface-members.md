---
title: 'Procedimiento Implementar explícitamente miembros de interfaz: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: dff094aca237ed6146bd9b52813c40549bc99b9b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627790"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="33bd5-102">Procedimiento Implementar explícitamente miembros de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="33bd5-102">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="33bd5-103">Este ejemplo declara una [interfaz](../../language-reference/keywords/interface.md), `IDimensions`, y una clase, `Box`, que implementa explícitamente los miembros de interfaz `GetLength` y `GetWidth`.</span><span class="sxs-lookup"><span data-stu-id="33bd5-103">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="33bd5-104">Se tiene acceso a los miembros mediante la instancia de interfaz `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="33bd5-104">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33bd5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33bd5-105">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="33bd5-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="33bd5-106">Robust Programming</span></span>  
  
- <span data-ttu-id="33bd5-107">Tenga en cuenta que las siguientes líneas, en el método `Main`, se comentan porque producirían errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="33bd5-107">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="33bd5-108">No se puede tener acceso a un miembro de interfaz que se implementa explícitamente desde una instancia [class](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="33bd5-108">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="33bd5-109">Tenga en cuenta también que las líneas siguientes, en el método `Main`, imprimen correctamente las dimensiones del cuadro porque se llama a los métodos desde una instancia de la interfaz:</span><span class="sxs-lookup"><span data-stu-id="33bd5-109">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="33bd5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="33bd5-110">See also</span></span>

- [<span data-ttu-id="33bd5-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="33bd5-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="33bd5-112">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="33bd5-112">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="33bd5-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="33bd5-113">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="33bd5-114">Procedimiento para implementar miembros de dos interfaces de forma explícita</span><span class="sxs-lookup"><span data-stu-id="33bd5-114">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
