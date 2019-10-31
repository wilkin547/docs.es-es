---
title: Campo ServicePointManager. s_ServicePointTable
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68445f4a290b9f4fe2696e35cda391b6c0ee8f85
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119995"
---
# <a name="servicepointmanagers_servicepointtable-field"></a><span data-ttu-id="becfc-102">ServicePointManager. s\_campo ServicePointTable</span><span class="sxs-lookup"><span data-stu-id="becfc-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="becfc-103">`ServicePointManager.s_ServicePointTable` es una <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="becfc-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="becfc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="becfc-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="becfc-105">El campo `ServicePointManager.s_ServicePointTable` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="becfc-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="becfc-106">Microsoft no admite el uso de este campo en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="becfc-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="becfc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="becfc-107">Requirements</span></span>

<span data-ttu-id="becfc-108">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="becfc-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="becfc-109">**Ensamblado:** Sistema (en System. dll)</span><span class="sxs-lookup"><span data-stu-id="becfc-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="becfc-110">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="becfc-110">**.NET Framework versions:** Available since 2.0.</span></span>
