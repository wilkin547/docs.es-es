---
title: HttpWebRequest._CoreResponse Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e6493747cf6c894357223f011da026770778e26c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="httpwebrequestcoreresponse-field"></a><span data-ttu-id="0f0d6-102">HttpWebRequest. \_CoreResponse campo</span><span class="sxs-lookup"><span data-stu-id="0f0d6-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="0f0d6-103">`HttpWebRequest._CoreResponse`es un objeto (ya sea un [CoreResponseData](coreresponsedata.md) o <xref:System.Exception>) que contiene el resultado del análisis de respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="0f0d6-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f0d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f0d6-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="0f0d6-105">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0f0d6-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="0f0d6-106">En su lugar, debe usar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de la red.</span><span class="sxs-lookup"><span data-stu-id="0f0d6-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="0f0d6-107">Vea [manual del usuario de DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="0f0d6-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="0f0d6-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0f0d6-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f0d6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f0d6-109">Requirements</span></span>

<span data-ttu-id="0f0d6-110">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0f0d6-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0f0d6-111">**Ensamblado:** sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="0f0d6-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="0f0d6-112">**Versiones de .NET framework:** disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="0f0d6-112">**.NET Framework versions:** Available since 2.0.</span></span>
