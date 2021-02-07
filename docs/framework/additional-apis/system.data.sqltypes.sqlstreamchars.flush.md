---
description: 'Más información sobre: SqlStreamChars. Flush (método)'
title: Método SqlStreamChars. Flush (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 8f519ffb8248a17608319eb0fbfe598f9ee3487a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684469"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="983c5-103">SqlStreamChars. Flush (método)</span><span class="sxs-lookup"><span data-stu-id="983c5-103">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="983c5-104">Cuando se reemplaza en una clase derivada, borra todos los búferes de esta secuencia y hace que todos los datos almacenados en el búfer se escriban en el dispositivo subyacente.</span><span class="sxs-lookup"><span data-stu-id="983c5-104">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="983c5-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="983c5-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="983c5-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="983c5-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="983c5-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="983c5-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="983c5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="983c5-108">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="983c5-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="983c5-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="983c5-110">El `SqlStreamChars.Flush` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="983c5-110">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="983c5-111">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="983c5-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="983c5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="983c5-112">Requirements</span></span>

<span data-ttu-id="983c5-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="983c5-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="983c5-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="983c5-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="983c5-115">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="983c5-115">**.NET Framework versions:** Available since 2.0.</span></span>
