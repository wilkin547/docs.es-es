---
title: ServicePointManager. s_ServicePointTable campo
description: Lea sobre el campo ServicePointManager. s_ServicePointTable en .NET. Este campo de tabla hash contiene conexiones HTTP activas (ServicePoints) en el AppDomain.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
ms.openlocfilehash: 9462ae10125dd37706f786a1f2cef78e62fbabcc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989539"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="f1627-104">Campo ServicePointManager. s \_ ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="f1627-104">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="f1627-105">`ServicePointManager.s_ServicePointTable`es un <xref:System.Collections.Hashtable> que contiene la lista de conexiones http activas <xref:System.Net.ServicePoint> en <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="f1627-105">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1627-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1627-106">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="f1627-107">El `ServicePointManager.s_ServicePointTable` campo es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="f1627-107">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f1627-108">Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="f1627-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1627-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1627-109">Requirements</span></span>

<span data-ttu-id="f1627-110">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="f1627-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="f1627-111">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="f1627-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f1627-112">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1627-112">**.NET Framework versions:** Available since 2.0.</span></span>
