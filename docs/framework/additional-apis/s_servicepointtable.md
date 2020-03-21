---
title: ServicePointManager.s_ServicePointTable Field
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
ms.openlocfilehash: 6a56ecd6fc85005f5987c3c2ad0d1680ca63c398
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155824"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="2ce34-102">Campo ServicePointManager.s\_ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="2ce34-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="2ce34-103">`ServicePointManager.s_ServicePointTable`es <xref:System.Collections.Hashtable> un que contiene la lista<xref:System.Net.ServicePoint>de conexiones HTTP activas ( s) en el <xref:System.AppDomain>archivo .</span><span class="sxs-lookup"><span data-stu-id="2ce34-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="2ce34-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ce34-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="2ce34-105">El `ServicePointManager.s_ServicePointTable` campo es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="2ce34-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2ce34-106">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="2ce34-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2ce34-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ce34-107">Requirements</span></span>

<span data-ttu-id="2ce34-108">**Espacio de nombres:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="2ce34-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="2ce34-109">**Montaje:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="2ce34-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="2ce34-110">**Versiones de .NET Framework:** Disponible desde 2.0.</span><span class="sxs-lookup"><span data-stu-id="2ce34-110">**.NET Framework versions:** Available since 2.0.</span></span>
