---
title: Campo HttpWebRequest. _CoreResponse
description: Lea sobre el campo HttpWebRequest. _CoreResponse en .NET. Este campo es un objeto CoreResponseData o Exception que contiene el resultado del análisis de respuesta HTTP.
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
ms.openlocfilehash: 5093ec7ed2c3b94931dcd622ae9ccdb42feffa18
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989748"
---
# <a name="httpwebrequest_coreresponse-field"></a><span data-ttu-id="0a91a-104">HttpWebRequest. \_ Campo CoreResponse</span><span class="sxs-lookup"><span data-stu-id="0a91a-104">HttpWebRequest.\_CoreResponse Field</span></span>

<span data-ttu-id="0a91a-105">`HttpWebRequest._CoreResponse`es un objeto ( [CoreResponseData](coreresponsedata.md) o un <xref:System.Exception> ) que contiene el resultado del análisis de respuesta http.</span><span class="sxs-lookup"><span data-stu-id="0a91a-105">`HttpWebRequest._CoreResponse` is an object (either a [CoreResponseData](coreresponsedata.md) or an <xref:System.Exception>) containing the result of HTTP response parsing.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a91a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a91a-106">Syntax</span></span>
  
```csharp
private object _CoreResponse
```

> [!WARNING]
> <span data-ttu-id="0a91a-107">Esta API no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0a91a-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="0a91a-108">En su lugar, debe utilizar un <xref:System.Diagnostics.DiagnosticSource> para enlazar el código de red.</span><span class="sxs-lookup"><span data-stu-id="0a91a-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="0a91a-109">Consulte [la guía del usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="0a91a-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="0a91a-110">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0a91a-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a91a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a91a-111">Requirements</span></span>

<span data-ttu-id="0a91a-112">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0a91a-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0a91a-113">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="0a91a-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="0a91a-114">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="0a91a-114">**.NET Framework versions:** Available since 2.0.</span></span>
