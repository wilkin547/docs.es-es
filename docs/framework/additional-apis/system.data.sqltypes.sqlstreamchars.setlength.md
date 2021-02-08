---
description: 'Más información sobre: SqlStreamChars. SetLength (Int64) (método)'
title: Método SqlStreamChars. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d10ce55126ae09062fe895c3a686ce5d94174554
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804145"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="a8ab5-103">SqlStreamChars. SetLength (Int64) (método)</span><span class="sxs-lookup"><span data-stu-id="a8ab5-103">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="a8ab5-104">Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-104">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="a8ab5-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a8ab5-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a8ab5-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="a8ab5-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8ab5-108">Parameters</span></span>

`value`\
<span data-ttu-id="a8ab5-109">Longitud deseada de la secuencia actual, en bytes.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-109">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8ab5-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a8ab5-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a8ab5-111">El `SqlStreamChars.SetLength` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-111">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a8ab5-112">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8ab5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8ab5-113">Requirements</span></span>

<span data-ttu-id="a8ab5-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a8ab5-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a8ab5-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="a8ab5-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a8ab5-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="a8ab5-116">**.NET Framework versions:** Available since 2.0.</span></span>
