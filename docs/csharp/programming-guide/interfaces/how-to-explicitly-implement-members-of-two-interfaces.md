---
title: 'Procedimiento Implementar explícitamente miembros de dos interfaces: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c7adc08f62a7f8a14b8e10f8b5ecdd6e37db811d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75701243"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="d1876-102">Procedimiento Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d1876-102">How to explicitly implement members of two interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="d1876-103">La implementación explícita de [interfaces](../../language-reference/keywords/interface.md) también permite al programador implementar dos interfaces que tienen los mismos nombres de miembros y dar a cada miembro de una interfaz una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="d1876-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="d1876-104">En este ejemplo se muestran las dimensiones de un cuadro en unidades métricas e inglesas.</span><span class="sxs-lookup"><span data-stu-id="d1876-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="d1876-105">La [clase](../../language-reference/keywords/class.md) Box implementa dos interfaces, IEnglishDimensions e IMetricDimensions, que representan los diferentes sistemas de medida.</span><span class="sxs-lookup"><span data-stu-id="d1876-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="d1876-106">Ambas interfaces tienen nombres de miembros idénticos, Length y Width.</span><span class="sxs-lookup"><span data-stu-id="d1876-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1876-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1876-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d1876-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d1876-108">Robust Programming</span></span>  
 <span data-ttu-id="d1876-109">Si quiere realizar las medidas en unidades inglesas de manera predeterminada, implemente los métodos Length y Width con normalidad e implemente explícitamente los métodos Length y Width de la interfaz IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="d1876-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="d1876-110">En este caso, se puede tener acceso a las unidades inglesas desde la instancia de clase y acceso a las unidades métricas desde la instancia de interfaz:</span><span class="sxs-lookup"><span data-stu-id="d1876-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d1876-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1876-111">See also</span></span>

- [<span data-ttu-id="d1876-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d1876-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d1876-113">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="d1876-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="d1876-114">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d1876-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="d1876-115">Procedimiento para implementar miembros de interfaz de forma explícita</span><span class="sxs-lookup"><span data-stu-id="d1876-115">How to explicitly implement interface members</span></span>](./how-to-explicitly-implement-interface-members.md)
