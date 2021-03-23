---
title: HttpWebRequest._CoreResponse campo
description: Lea sobre el campo HttpWebRequest._CoreResponse en .NET. Este campo es un objeto CoreResponseData o Exception que contiene el resultado del análisis de respuesta HTTP.
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
ms.openlocfilehash: f5fb71c21922285c0e18c2d1f28eeaf2353dcaee
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873840"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="691db-104">HttpWebRequest. \_ Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="691db-104">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="691db-105">`HttpWebRequest._CoreResponse` es un objeto ( [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception> ) que contiene el resultado del análisis de respuesta http.</span><span class="sxs-lookup"><span data-stu-id="691db-105">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="691db-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="691db-106">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="691db-107">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="691db-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="691db-108">En su lugar, debe utilizar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="691db-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="691db-109">Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="691db-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="691db-110">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="691db-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="691db-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="691db-111">Requirements</span></span>

<span data-ttu-id="691db-112">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="691db-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="691db-113">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="691db-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="691db-114">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="691db-114">**.NET Framework versions:** Available since 2.0.</span></span>
