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
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="fbcf8-104">Procedimiento Implementar explícitamente miembros de interfaz (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fbcf8-104">How to explicitly implement interface members (C# Programming Guide)</span></span>
<span data-ttu-id="fbcf8-105">Este ejemplo declara una [interfaz](../../language-reference/keywords/interface.md), `IDimensions`, y una clase, `Box`, que implementa explícitamente los miembros de interfaz `GetLength` y `GetWidth`.</span><span class="sxs-lookup"><span data-stu-id="fbcf8-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="fbcf8-106">Se tiene acceso a los miembros mediante la instancia de interfaz `dimensions`.</span><span class="sxs-lookup"><span data-stu-id="fbcf8-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbcf8-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbcf8-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fbcf8-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fbcf8-108">Robust Programming</span></span>  
  
- <span data-ttu-id="fbcf8-109">Tenga en cuenta que las siguientes líneas, en el método `Main`, se comentan porque producirían errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="fbcf8-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="fbcf8-110">No se puede tener acceso a un miembro de interfaz que se implementa explícitamente desde una instancia [class](../../language-reference/keywords/class.md):</span><span class="sxs-lookup"><span data-stu-id="fbcf8-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="fbcf8-111">Tenga en cuenta también que las líneas siguientes, en el método `Main`, imprimen correctamente las dimensiones del cuadro porque se llama a los métodos desde una instancia de la interfaz:</span><span class="sxs-lookup"><span data-stu-id="fbcf8-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="fbcf8-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbcf8-112">See also</span></span>

- [<span data-ttu-id="fbcf8-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fbcf8-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fbcf8-114">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="fbcf8-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="fbcf8-115">Interfaces</span><span class="sxs-lookup"><span data-stu-id="fbcf8-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="fbcf8-116">Procedimiento para implementar miembros de dos interfaces de forma explícita</span><span class="sxs-lookup"><span data-stu-id="fbcf8-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
