---
title: 'NETSDK1013: No se ha reconocido el valor TargetFramework.'
description: Procedimiento para determinar y establecer un valor TargetFramework válido
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: 915ac22ad822d17c082498b469acbfb3f1a93efc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717881"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: No se ha reconocido el valor TargetFramework

**Este artículo se aplica a: ✔️** SDK de .NET Core 3.1.100 y versiones posteriores

El SDK intenta analizar los valores proporcionados en el archivo del proyecto para `<TargetFramework>` o `<TargetFrameworks>` en un valor conocido.  Si no se reconoce, el valor `TargetFrameworkIdentifier` o `TargetFrameworkVersion` se puede establecer en una cadena vacía o `Unsupported`.

Para solucionarlo, compruebe la ortografía del valor `TargetFramework` en la lista de [marcos admitidos](../../../standard/frameworks.md).
También puede establecer las propiedades `TargetFrameworkIdentifier` y `TargetFrameworkVersion` directamente en el archivo del proyecto.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
