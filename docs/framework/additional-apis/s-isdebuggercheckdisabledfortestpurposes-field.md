---
title: s_isDebuggerCheckDisabledForTestPurposes campo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
robots: noindex,nofollow
ms.workload:
- dotnet
ms.openlocfilehash: 67da38d958d153ebe526f298785b39afb7be6513
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="2a5ea-102">s_isDebuggerCheckDisabledForTestPurposes campo</span><span class="sxs-lookup"><span data-stu-id="2a5ea-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="2a5ea-103">Este campo privado en la `System.Windows.Diagnostics.VisualDiagnostics` clase se utiliza Visual Studio para determinar si se realizará una comprobación interna de un depurador activo.</span><span class="sxs-lookup"><span data-stu-id="2a5ea-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a5ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a5ea-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="2a5ea-105">API en el `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="2a5ea-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="2a5ea-106">Establecer `s_isDebuggerCheckDisabledForTestPurposes` a `true` para tener acceso a las API fuera de un depurador.</span><span class="sxs-lookup"><span data-stu-id="2a5ea-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="2a5ea-107">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="2a5ea-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="2a5ea-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a5ea-108">Requirements</span></span>

<span data-ttu-id="2a5ea-109">**Namespace:**<xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="2a5ea-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="2a5ea-110">**Ensamblado:** PresentationCore (en PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="2a5ea-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="2a5ea-111">**Versiones de .NET framework:** disponible desde la versión 4.6.</span><span class="sxs-lookup"><span data-stu-id="2a5ea-111">**.NET Framework versions:** Available since 4.6.</span></span>
