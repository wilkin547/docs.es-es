---
description: 'Más información sobre: SqlStreamChars. Dispose (Boolean) (método)'
title: Método SqlStreamChars. Dispose (Boolean) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Dispose
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ce24cc885d87a3ff0bbcdbea7992ca78ee592454
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802611"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="07ebb-103">SqlStreamChars. Dispose (Boolean) (método)</span><span class="sxs-lookup"><span data-stu-id="07ebb-103">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="07ebb-104">Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="07ebb-104">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="07ebb-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="07ebb-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="07ebb-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07ebb-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="07ebb-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="07ebb-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="07ebb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07ebb-108">Parameters</span></span>

`disposing`\
<span data-ttu-id="07ebb-109">Es `true` para liberar tanto recursos administrados como no administrados; es `false` para liberar únicamente recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="07ebb-109">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="07ebb-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="07ebb-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="07ebb-111">El `SqlStreamChars.Dispose` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="07ebb-111">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="07ebb-112">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="07ebb-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="07ebb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07ebb-113">Requirements</span></span>

<span data-ttu-id="07ebb-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="07ebb-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="07ebb-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="07ebb-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="07ebb-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="07ebb-116">**.NET Framework versions:** Available since 2.0.</span></span>
