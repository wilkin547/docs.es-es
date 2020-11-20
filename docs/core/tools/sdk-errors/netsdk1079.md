---
title: 'NETSDK1079: El paquete Microsoft.AspNetCore.All no se admite cuando el destino es .NET Core 3.0 o posterior.'
description: Procedimiento para resolver la migración fuera de Microsoft.AspNetCore.App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445707"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a>NETSDK1079: El paquete Microsoft.AspNetCore.All no se admite cuando el destino es .NET Core 3.0 o posterior.

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.100 y versiones posteriores

Es posible que reciba este mensaje de error en los siguientes casos:

- Puede redestinar un proyecto de ASP.NET Core de .NET Core 2.2 o anterior a .NET Core 3.0 o posterior.
- El proyecto usa el paquete Microsoft.AspNetCore.All.

Quite `PackageReference` para Microsoft.AspNetCore.All.  También es posible que deba agregar referencias para los paquetes a los que se hace referencia desde Microsoft.AspNetCore.All, pero que no se incluyen en el marco compartido de ASP.NET Core.  Estos paquetes se enumeran aquí: [Migración desde Microsoft.AspNetCore.All a Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).

Vea también [Migración desde ASP.NET Core 2.2 a 3.0](/aspnet/core/migration/22-to-30)
