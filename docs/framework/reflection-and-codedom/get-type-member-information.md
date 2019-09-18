---
title: Procedimiento para obtener información sobre tipos y miembros mediante la reflexión
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972862"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="d3ce6-102">Procedimiento para obtener información sobre tipos y miembros mediante la reflexión</span><span class="sxs-lookup"><span data-stu-id="d3ce6-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="d3ce6-103">El espacio de nombres <xref:System.Reflection> contiene muchos métodos para obtener información sobre los tipos y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="d3ce6-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="d3ce6-104">En este artículo se muestra uno de estos métodos, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3ce6-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d3ce6-105">Para obtener más información, vea [Reflexión en .NET](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="d3ce6-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="d3ce6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3ce6-106">Example</span></span>

<span data-ttu-id="d3ce6-107">En el ejemplo siguiente se obtiene información sobre tipos y miembros mediante la reflexión:</span><span class="sxs-lookup"><span data-stu-id="d3ce6-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="d3ce6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3ce6-108">See also</span></span>

- [<span data-ttu-id="d3ce6-109">Programación con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d3ce6-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="d3ce6-110">Reflexión</span><span class="sxs-lookup"><span data-stu-id="d3ce6-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="d3ce6-111">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="d3ce6-111">Use application domains</span></span>](../app-domains/use.md)
