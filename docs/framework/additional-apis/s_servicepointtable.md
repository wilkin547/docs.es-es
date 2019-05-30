---
title: Campo ServicePointManager.s_ServicePointTable
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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 840d068d282e3ba35df5aee6a11ff96d9e6bfdbd
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301392"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="54b38-102">ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="54b38-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="54b38-103">`ServicePointManager.s_ServicePointTable` es un <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="54b38-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="54b38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54b38-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="54b38-105">El `ServicePointManager.s_ServicePointTable` campo es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="54b38-105">The `ServicePointManager.s_ServicePointTable` field is private and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="54b38-106">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="54b38-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="54b38-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54b38-107">Requirements</span></span>

<span data-ttu-id="54b38-108">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="54b38-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="54b38-109">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="54b38-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="54b38-110">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="54b38-110">**.NET Framework versions:** Available since 2.0.</span></span>
