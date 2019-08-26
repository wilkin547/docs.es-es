---
title: 'Procedimiento Implementar explícitamente miembros de dos interfaces: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 1d4dd0485be1d859e3e9594ab1558a907b8f1f7a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589198"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="177bd-102">Procedimiento Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="177bd-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="177bd-103">La implementación explícita de [interfaces](../../language-reference/keywords/interface.md) también permite al programador implementar dos interfaces que tienen los mismos nombres de miembros y dar a cada miembro de una interfaz una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="177bd-103">Explicit [interface](../../language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="177bd-104">En este ejemplo se muestran las dimensiones de un cuadro en unidades métricas e inglesas.</span><span class="sxs-lookup"><span data-stu-id="177bd-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="177bd-105">La [clase](../../language-reference/keywords/class.md) Box implementa dos interfaces, IEnglishDimensions e IMetricDimensions, que representan los diferentes sistemas de medida.</span><span class="sxs-lookup"><span data-stu-id="177bd-105">The Box [class](../../language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="177bd-106">Ambas interfaces tienen nombres de miembros idénticos, Length y Width.</span><span class="sxs-lookup"><span data-stu-id="177bd-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="177bd-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="177bd-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#9)]  
  
## <a name="robust-programming"></a><span data-ttu-id="177bd-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="177bd-108">Robust Programming</span></span>  
 <span data-ttu-id="177bd-109">Si quiere realizar las medidas en unidades inglesas de manera predeterminada, implemente los métodos Length y Width con normalidad e implemente explícitamente los métodos Length y Width de la interfaz IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="177bd-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#10)]  
  
 <span data-ttu-id="177bd-110">En este caso, se puede tener acceso a las unidades inglesas desde la instancia de clase y acceso a las unidades métricas desde la instancia de interfaz:</span><span class="sxs-lookup"><span data-stu-id="177bd-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="177bd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="177bd-111">See also</span></span>

- [<span data-ttu-id="177bd-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="177bd-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="177bd-113">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="177bd-113">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="177bd-114">Interfaces</span><span class="sxs-lookup"><span data-stu-id="177bd-114">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="177bd-115">Cómo: Implementar explícitamente miembros de interfaz</span><span class="sxs-lookup"><span data-stu-id="177bd-115">How to: Explicitly Implement Interface Members</span></span>](./how-to-explicitly-implement-interface-members.md)
