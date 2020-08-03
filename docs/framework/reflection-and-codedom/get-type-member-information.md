---
title: Procedimiento para obtener información sobre tipos y miembros mediante la reflexión
description: Aprenda a obtener información sobre tipos y miembros con reflexión mediante el uso del espacio de nombres System.Reflection.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: fa7af39c0addb328944a03236c26982301caf722
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865325"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="e6c4a-103">Procedimiento para obtener información sobre tipos y miembros mediante la reflexión</span><span class="sxs-lookup"><span data-stu-id="e6c4a-103">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="e6c4a-104">El espacio de nombres <xref:System.Reflection> contiene muchos métodos para obtener información sobre los tipos y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="e6c4a-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="e6c4a-105">En este artículo se muestra uno de estos métodos, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e6c4a-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e6c4a-106">Para obtener más información, vea [Reflexión en .NET](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="e6c4a-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="e6c4a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6c4a-107">Example</span></span>

<span data-ttu-id="e6c4a-108">En el ejemplo siguiente se obtiene información sobre tipos y miembros mediante la reflexión:</span><span class="sxs-lookup"><span data-stu-id="e6c4a-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="e6c4a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6c4a-109">See also</span></span>

- [<span data-ttu-id="e6c4a-110">Programación con dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="e6c4a-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="e6c4a-111">Reflexión</span><span class="sxs-lookup"><span data-stu-id="e6c4a-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="e6c4a-112">Utilizar dominios de aplicación</span><span class="sxs-lookup"><span data-stu-id="e6c4a-112">Use application domains</span></span>](../app-domains/use.md)
