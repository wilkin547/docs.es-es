---
title: Campo de ServicePointManager.s_ServicePointTable
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
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 5450a0cb3e5bd39a86365b16d372c7e573a43496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351763"
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="13739-102">ServicePointManager.s\_ServicePointTable campo</span><span class="sxs-lookup"><span data-stu-id="13739-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="13739-103">`ServicePointManager.s_ServicePointTable` es un <xref:System.Collections.Hashtable> que contiene la lista de conexiones HTTP activas (<xref:System.Net.ServicePoint>s) en el <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="13739-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="13739-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13739-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="13739-105">El `ServicePointManager.s_ServicePointTable` campo es privado y no están hechos para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="13739-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="13739-106">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="13739-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="13739-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13739-107">Requirements</span></span>

<span data-ttu-id="13739-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="13739-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="13739-109">**Ensamblado:** sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="13739-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="13739-110">**Versiones de .NET framework:** disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="13739-110">**.NET Framework versions:** Available since 2.0.</span></span>
