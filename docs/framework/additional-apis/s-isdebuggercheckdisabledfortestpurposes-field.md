---
description: 'Más información acerca de: s_isDebuggerCheckDisabledForTestPurposes campo'
title: s_isDebuggerCheckDisabledForTestPurposes campo
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: a71235c13a7a35872bcf5374be8077bafad5ff9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802663"
---
# <a name="s_isdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="ff882-103">s_isDebuggerCheckDisabledForTestPurposes campo</span><span class="sxs-lookup"><span data-stu-id="ff882-103">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="ff882-104">Visual Studio usa este campo privado de la `System.Windows.Diagnostics.VisualDiagnostics` clase para determinar si se realizará una comprobación interna de un depurador activo.</span><span class="sxs-lookup"><span data-stu-id="ff882-104">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff882-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff882-105">Syntax</span></span>

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> <span data-ttu-id="ff882-106">Las API de la `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="ff882-106">APIs in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="ff882-107">Establezca `s_isDebuggerCheckDisabledForTestPurposes` en `true` para tener acceso a las API fuera de un depurador.</span><span class="sxs-lookup"><span data-stu-id="ff882-107">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>
>
> <span data-ttu-id="ff882-108">Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ff882-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff882-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff882-109">Requirements</span></span>

<span data-ttu-id="ff882-110">**Espacio de nombres:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="ff882-110">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="ff882-111">**Ensamblado:** PresentationCore (en PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="ff882-111">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="ff882-112">**.NET Framework versiones:** Disponible desde 4,6.</span><span class="sxs-lookup"><span data-stu-id="ff882-112">**.NET Framework versions:** Available since 4.6.</span></span>
