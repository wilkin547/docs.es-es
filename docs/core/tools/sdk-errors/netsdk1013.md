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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="81c12-103">NETSDK1013: No se ha reconocido el valor TargetFramework</span><span class="sxs-lookup"><span data-stu-id="81c12-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="81c12-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 3.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="81c12-104">**This article applies to:** ✔️ .NET Core 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="81c12-105">El SDK intenta analizar los valores proporcionados en el archivo del proyecto para `<TargetFramework>` o `<TargetFrameworks>` en un valor conocido.</span><span class="sxs-lookup"><span data-stu-id="81c12-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="81c12-106">Si no se reconoce, el valor `TargetFrameworkIdentifier` o `TargetFrameworkVersion` se puede establecer en una cadena vacía o `Unsupported`.</span><span class="sxs-lookup"><span data-stu-id="81c12-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="81c12-107">Para solucionarlo, compruebe la ortografía del valor `TargetFramework` en la lista de [marcos admitidos](../../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="81c12-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="81c12-108">También puede establecer las propiedades `TargetFrameworkIdentifier` y `TargetFrameworkVersion` directamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81c12-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
