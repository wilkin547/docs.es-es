---
title: 'Cómo: Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: c3a804ce1bf1f5ac8db47f0f0c1f37d1ca5f781b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213178"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="98055-102">Cómo: Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="98055-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="98055-103">Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin asignar un campo a cada evento, pero usando en su lugar un diccionario para almacenar las instancias del evento.</span><span class="sxs-lookup"><span data-stu-id="98055-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="98055-104">Esto solo es útil si tiene muchos eventos, pero espera que la mayoría de ellos no se implemente.</span><span class="sxs-lookup"><span data-stu-id="98055-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98055-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98055-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="98055-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="98055-106">See Also</span></span>

- [<span data-ttu-id="98055-107">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="98055-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="98055-108">Eventos</span><span class="sxs-lookup"><span data-stu-id="98055-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
- [<span data-ttu-id="98055-109">Delegados</span><span class="sxs-lookup"><span data-stu-id="98055-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
