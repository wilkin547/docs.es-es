---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802861"
---

> [!WARNING]
> <span data-ttu-id="fa5ae-101">Cuando se usa <xref:System.Text.RegularExpressions> para procesar entradas que no son de confianza, pase un tiempo de expiración.</span><span class="sxs-lookup"><span data-stu-id="fa5ae-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="fa5ae-102">Un usuario malintencionado puede proporcionar entradas a `RegularExpressions` y provocar un [ataque por denegación de servicio](https://www.us-cert.gov/ncas/tips/ST04-015).</span><span class="sxs-lookup"><span data-stu-id="fa5ae-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="fa5ae-103">Las API del marco ASP.NET Core en las que se usa `RegularExpressions` pasan un tiempo de expiración.</span><span class="sxs-lookup"><span data-stu-id="fa5ae-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
