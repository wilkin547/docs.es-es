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
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a><span data-ttu-id="cdb2c-103">NETSDK1013: No se ha reconocido el valor TargetFramework</span><span class="sxs-lookup"><span data-stu-id="cdb2c-103">NETSDK1013: The TargetFramework value was not recognized</span></span>

<span data-ttu-id="cdb2c-104">**Este artículo se aplica a:** ✔️ SDK de .NET 3.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="cdb2c-104">**This article applies to:** ✔️ .NET 3.1.100 SDK and later versions</span></span>

<span data-ttu-id="cdb2c-105">El SDK intenta analizar los valores proporcionados en el archivo del proyecto para `<TargetFramework>` o `<TargetFrameworks>` en un valor conocido.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-105">The SDK tries to parse the values provided in the project file for `<TargetFramework>` or `<TargetFrameworks>` into a well known value.</span></span>  <span data-ttu-id="cdb2c-106">Si no se reconoce, el valor `TargetFrameworkIdentifier` o `TargetFrameworkVersion` se puede establecer en una cadena vacía o `Unsupported`.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-106">If the value is not recognized, the `TargetFrameworkIdentifier` or `TargetFrameworkVersion` value may be set to an empty string or `Unsupported`.</span></span>

<span data-ttu-id="cdb2c-107">Para solucionarlo, compruebe la ortografía del valor `TargetFramework` en la lista de [marcos admitidos](../../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="cdb2c-107">To resolve this, check the spelling of your `TargetFramework` value from the list of [supported frameworks](../../../standard/frameworks.md).</span></span>
<span data-ttu-id="cdb2c-108">También puede establecer las propiedades `TargetFrameworkIdentifier` y `TargetFrameworkVersion` directamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="cdb2c-108">You can also set the `TargetFrameworkIdentifier` and `TargetFrameworkVersion` properties directly in your project file.</span></span>

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
