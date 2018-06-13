---
title: 'Cómo: Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 97a7b0f168e4a1c81ec396f42b731dabb45b3516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327221"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="fcad1-102">Cómo: Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fcad1-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="fcad1-103">Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin asignar un campo a cada evento, pero usando en su lugar un diccionario para almacenar las instancias del evento.</span><span class="sxs-lookup"><span data-stu-id="fcad1-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="fcad1-104">Esto solo es útil si tiene muchos eventos, pero espera que la mayoría de ellos no se implemente.</span><span class="sxs-lookup"><span data-stu-id="fcad1-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcad1-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcad1-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fcad1-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcad1-106">See Also</span></span>  
 [<span data-ttu-id="fcad1-107">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fcad1-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fcad1-108">Eventos</span><span class="sxs-lookup"><span data-stu-id="fcad1-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="fcad1-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="fcad1-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
