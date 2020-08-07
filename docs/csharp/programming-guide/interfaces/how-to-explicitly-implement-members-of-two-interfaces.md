---
title: 'Procedimiento Implementar explícitamente miembros de dos interfaces: Guía de programación de C#'
description: Aprenda a implementar explícitamente dos interfaces que tengan los mismos nombres de miembro y asigne a cada miembro de interfaz una implementación independiente en este ejemplo de C#.
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: d60ec43f734d5e8bfa7f467874440bd3514877fe
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303067"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="ca64e-103">Procedimiento Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ca64e-103">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ca64e-104">La implementación explícita de [interfaces](../../language-reference/keywords/interface.md) también permite al programador implementar dos interfaces que tienen los mismos nombres de miembros y dar a cada miembro de una interfaz una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="ca64e-104">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="ca64e-105">En este ejemplo se muestran las dimensiones de un cuadro en unidades métricas e inglesas.</span><span class="sxs-lookup"><span data-stu-id="ca64e-105">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="ca64e-106">La [clase](../../language-reference/keywords/class.md) Box implementa dos interfaces, IEnglishDimensions e IMetricDimensions, que representan los diferentes sistemas de medida.</span><span class="sxs-lookup"><span data-stu-id="ca64e-106">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="ca64e-107">Ambas interfaces tienen nombres de miembros idénticos, Length y Width.</span><span class="sxs-lookup"><span data-stu-id="ca64e-107">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca64e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca64e-108">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ca64e-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ca64e-109">Robust Programming</span></span>  
 <span data-ttu-id="ca64e-110">Si quiere realizar las medidas en unidades inglesas de manera predeterminada, implemente los métodos Length y Width con normalidad e implemente explícitamente los métodos Length y Width de la interfaz IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="ca64e-110">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="ca64e-111">En este caso, se puede tener acceso a las unidades inglesas desde la instancia de clase y acceso a las unidades métricas desde la instancia de interfaz:</span><span class="sxs-lookup"><span data-stu-id="ca64e-111">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="ca64e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca64e-112">See also</span></span>

- [<span data-ttu-id="ca64e-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ca64e-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ca64e-114">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="ca64e-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="ca64e-115">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ca64e-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="ca64e-116">Procedimiento para implementar miembros de interfaz de forma explícita</span><span class="sxs-lookup"><span data-stu-id="ca64e-116">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
