---
title: 'Cómo: Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: 6c02585b57acef654c6613bef1a276a433763af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514678"
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a><span data-ttu-id="ad915-102">Cómo: Implementar explícitamente miembros de dos interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ad915-102">How to: Explicitly Implement Members of Two Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ad915-103">La implementación explícita de [interfaces](../../../csharp/language-reference/keywords/interface.md) también permite al programador implementar dos interfaces que tienen los mismos nombres de miembros y dar a cada miembro de una interfaz una implementación independiente.</span><span class="sxs-lookup"><span data-stu-id="ad915-103">Explicit [interface](../../../csharp/language-reference/keywords/interface.md) implementation also allows the programmer to implement two interfaces that have the same member names and give each interface member a separate implementation.</span></span> <span data-ttu-id="ad915-104">En este ejemplo se muestran las dimensiones de un cuadro en unidades métricas e inglesas.</span><span class="sxs-lookup"><span data-stu-id="ad915-104">This example displays the dimensions of a box in both metric and English units.</span></span> <span data-ttu-id="ad915-105">La [clase](../../../csharp/language-reference/keywords/class.md) Box implementa dos interfaces, IEnglishDimensions e IMetricDimensions, que representan los diferentes sistemas de medida.</span><span class="sxs-lookup"><span data-stu-id="ad915-105">The Box [class](../../../csharp/language-reference/keywords/class.md) implements two interfaces IEnglishDimensions and IMetricDimensions, which represent the different measurement systems.</span></span> <span data-ttu-id="ad915-106">Ambas interfaces tienen nombres de miembros idénticos, Length y Width.</span><span class="sxs-lookup"><span data-stu-id="ad915-106">Both interfaces have identical member names, Length and Width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad915-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad915-107">Example</span></span>  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ad915-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ad915-108">Robust Programming</span></span>  
 <span data-ttu-id="ad915-109">Si quiere realizar las medidas en unidades inglesas de manera predeterminada, implemente los métodos Length y Width con normalidad e implemente explícitamente los métodos Length y Width de la interfaz IMetricDimensions:</span><span class="sxs-lookup"><span data-stu-id="ad915-109">If you want to make the default measurements in English units, implement the methods Length and Width normally, and explicitly implement the Length and Width methods from the IMetricDimensions interface:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 <span data-ttu-id="ad915-110">En este caso, se puede tener acceso a las unidades inglesas desde la instancia de clase y acceso a las unidades métricas desde la instancia de interfaz:</span><span class="sxs-lookup"><span data-stu-id="ad915-110">In this case, you can access the English units from the class instance and access the metric units from the interface instance:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ad915-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad915-111">See Also</span></span>

- [<span data-ttu-id="ad915-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ad915-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ad915-113">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="ad915-113">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="ad915-114">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ad915-114">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
- [<span data-ttu-id="ad915-115">Cómo: Implementar explícitamente miembros de interfaz</span><span class="sxs-lookup"><span data-stu-id="ad915-115">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
