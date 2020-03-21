---
title: Campo HttpWebRequest._CoreResponse
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.HttpWebRequest._CoreResponse
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: b275f3eece96ac8a9ae3fb0ebd030c8d79e21fc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155926"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="a85da-102">HttpWebRequest. \_Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="a85da-102">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="a85da-103">`HttpWebRequest._CoreResponse`es un objeto (ya sea <xref:System.Exception> [CoreResponseData](coreresponsedata.md) o un ) que contiene el resultado del análisis de respuestas HTTP.</span><span class="sxs-lookup"><span data-stu-id="a85da-103">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="a85da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a85da-104">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="a85da-105">Esta API no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="a85da-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="a85da-106">En su lugar, <xref:System.Diagnostics.DiagnosticSource> debe usar a para enlazar código de red.</span><span class="sxs-lookup"><span data-stu-id="a85da-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="a85da-107">Consulte [Guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="a85da-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="a85da-108">Microsoft no admite el uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="a85da-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a85da-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a85da-109">Requirements</span></span>

<span data-ttu-id="a85da-110">**Espacio de nombres:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a85da-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a85da-111">**Montaje:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="a85da-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a85da-112">**Versiones de .NET Framework:** Disponible desde 2.0.</span><span class="sxs-lookup"><span data-stu-id="a85da-112">**.NET Framework versions:** Available since 2.0.</span></span>
