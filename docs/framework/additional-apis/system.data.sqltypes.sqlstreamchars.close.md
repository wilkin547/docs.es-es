---
title: Método SqlStreamChars.Close (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Close
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d0c29bbc5c6bea98cf36e3c2b6bf7825d6843ccc
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634029"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="d3611-102">Método SqlStreamChars.Close</span><span class="sxs-lookup"><span data-stu-id="d3611-102">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="d3611-103">Cierra la secuencia actual y libera los recursos del sistema asociados a la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d3611-103">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="d3611-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="d3611-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="d3611-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3611-105">It's intended for use by SQL Server.</span></span><span data-ttu-id="d3611-106"> Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="d3611-106"> For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="d3611-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3611-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d3611-108">El `SqlStreamChars.Close` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="d3611-108">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d3611-109">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="d3611-109">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d3611-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3611-110">Requirements</span></span>

<span data-ttu-id="d3611-111">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="d3611-111">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="d3611-112">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="d3611-112">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="d3611-113">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="d3611-113">**.NET Framework versions:** Available since 2.0.</span></span>