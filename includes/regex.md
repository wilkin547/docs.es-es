---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802861"
---

> [!WARNING]
> Cuando se usa <xref:System.Text.RegularExpressions> para procesar entradas que no son de confianza, pase un tiempo de expiración. Un usuario malintencionado puede proporcionar entradas a `RegularExpressions` y provocar un [ataque por denegación de servicio](https://www.us-cert.gov/ncas/tips/ST04-015). Las API del marco ASP.NET Core en las que se usa `RegularExpressions` pasan un tiempo de expiración.
