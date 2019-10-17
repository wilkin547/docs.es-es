---
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
ms.openlocfilehash: 44dc97835b8a7141064e8de4d2d5325c40be5a34
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395764"
---
# <a name="sqlstreamcharsdisposeboolean-method"></a><span data-ttu-id="0ab7d-102">SqlStreamChars. Dispose (Boolean) (método)</span><span class="sxs-lookup"><span data-stu-id="0ab7d-102">SqlStreamChars.Dispose(Boolean) Method</span></span>

<span data-ttu-id="0ab7d-103">Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="0ab7d-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0ab7d-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0ab7d-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
protected virtual void Dispose (bool disposing);
```

## <a name="parameters"></a><span data-ttu-id="0ab7d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ab7d-107">Parameters</span></span>

`disposing`\
<span data-ttu-id="0ab7d-108">Es `true` para liberar tanto recursos administrados como no administrados; es `false` para liberar únicamente recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-108">`true` to release both managed and unmanaged resources; `false` to release only unmanaged resources.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ab7d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ab7d-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0ab7d-110">El método `SqlStreamChars.Dispose` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-110">The `SqlStreamChars.Dispose` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0ab7d-111">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0ab7d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ab7d-112">Requirements</span></span>

<span data-ttu-id="0ab7d-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0ab7d-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0ab7d-114">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="0ab7d-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0ab7d-115">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="0ab7d-115">**.NET Framework versions:** Available since 2.0.</span></span>
