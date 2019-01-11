---
title: Campo s_isDebuggerCheckDisabledForTestPurposes
ms.date: 03/30/2017
ms.technology:
- dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ada3abcccac4244819cfbef1101a770761df6a50
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221926"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="9c721-102">Campo s_isDebuggerCheckDisabledForTestPurposes</span><span class="sxs-lookup"><span data-stu-id="9c721-102">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="9c721-103">Este campo privado en la `System.Windows.Diagnostics.VisualDiagnostics` clase se usa Visual Studio para determinar si se realizará una comprobación interna de un depurador activo.</span><span class="sxs-lookup"><span data-stu-id="9c721-103">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c721-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c721-104">Syntax</span></span>
  
```csharp  
private static bool s_isDebuggerCheckDisabledForTestPurposes
```
  
> [!WARNING]
>  <span data-ttu-id="9c721-105">API en el `System.Windows.Diagnostics.VisualDiagnostics` clase solo están disponibles cuando una aplicación se ejecuta bajo un depurador.</span><span class="sxs-lookup"><span data-stu-id="9c721-105">API's in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="9c721-106">Establecer `s_isDebuggerCheckDisabledForTestPurposes` a `true` para tener acceso a las API fuera de un depurador.</span><span class="sxs-lookup"><span data-stu-id="9c721-106">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>  
>   
>  <span data-ttu-id="9c721-107">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="9c721-107">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>  

## <a name="requirements"></a><span data-ttu-id="9c721-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c721-108">Requirements</span></span>

<span data-ttu-id="9c721-109">**Espacio de nombres:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="9c721-109">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="9c721-110">**Ensamblado:** PresentationCore (en PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="9c721-110">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="9c721-111">**Versiones de .NET framework:** Disponible desde la versión 4.6.</span><span class="sxs-lookup"><span data-stu-id="9c721-111">**.NET Framework versions:** Available since 4.6.</span></span>