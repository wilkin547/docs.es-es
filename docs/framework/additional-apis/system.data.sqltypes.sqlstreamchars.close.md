---
description: 'Más información sobre: SqlStreamChars. Close (método)'
title: Método SqlStreamChars. Close (System. Data. SqlTypes)
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
ms.openlocfilehash: 27f2ea6e288d166f3b63979a83a1cf80eeced334
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782382"
---
# <a name="sqlstreamcharsclose-method"></a><span data-ttu-id="e4569-103">SqlStreamChars. Close (método)</span><span class="sxs-lookup"><span data-stu-id="e4569-103">SqlStreamChars.Close Method</span></span>

<span data-ttu-id="e4569-104">Cierra la secuencia actual y libera todos los recursos del sistema asociados a la secuencia.</span><span class="sxs-lookup"><span data-stu-id="e4569-104">Closes the current stream and releases any system resources associated with the stream.</span></span> <span data-ttu-id="e4569-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="e4569-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e4569-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4569-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e4569-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="e4569-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public virtual void Close ();
```

## <a name="remarks"></a><span data-ttu-id="e4569-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4569-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e4569-109">El `SqlStreamChars.Close` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="e4569-109">The `SqlStreamChars.Close` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e4569-110">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="e4569-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4569-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4569-111">Requirements</span></span>

<span data-ttu-id="e4569-112">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e4569-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e4569-113">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="e4569-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e4569-114">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="e4569-114">**.NET Framework versions:** Available since 2.0.</span></span>
