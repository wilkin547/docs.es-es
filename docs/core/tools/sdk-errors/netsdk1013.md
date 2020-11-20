---
title: 'NETSDK1013: No se ha reconocido el valor TargetFramework.'
description: Procedimiento para determinar y establecer un valor TargetFramework válido
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: bcaed878b663f8bc957e8469ffd78caa9babf710
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445701"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: No se ha reconocido el valor TargetFramework

**Este artículo se aplica a:** ✔️ SDK de .NET 3.1.100 y versiones posteriores

El SDK intenta analizar los valores proporcionados en el archivo del proyecto para `<TargetFramework>` o `<TargetFrameworks>` en un valor conocido.  Si no se reconoce, el valor `TargetFrameworkIdentifier` o `TargetFrameworkVersion` se puede establecer en una cadena vacía o `Unsupported`.

Para solucionarlo, compruebe la ortografía del valor `TargetFramework` en la lista de [marcos admitidos](../../../standard/frameworks.md).
También puede establecer las propiedades `TargetFrameworkIdentifier` y `TargetFrameworkVersion` directamente en el archivo del proyecto.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
