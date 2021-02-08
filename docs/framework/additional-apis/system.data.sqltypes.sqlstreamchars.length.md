---
description: 'Más información sobre: SqlStreamChars. length (propiedad)'
title: Propiedad SqlStreamChars. length (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b0a9686cadc6d4018c7f291f0326b71195fd5cf5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802598"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="5a0c8-103">SqlStreamChars. length (propiedad)</span><span class="sxs-lookup"><span data-stu-id="5a0c8-103">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="5a0c8-104">Cuando se reemplaza en una clase derivada, obtiene la longitud de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-104">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="5a0c8-105">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="5a0c8-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="5a0c8-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="5a0c8-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a0c8-108">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="5a0c8-109">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="5a0c8-109">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="5a0c8-110">Longitud del flujo.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-110">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a0c8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a0c8-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="5a0c8-112">La `SqlStreamChars.Length` propiedad es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-112">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="5a0c8-113">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-113">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a0c8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a0c8-114">Requirements</span></span>

<span data-ttu-id="5a0c8-115">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="5a0c8-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="5a0c8-116">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="5a0c8-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="5a0c8-117">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="5a0c8-117">**.NET Framework versions:** Available since 2.0.</span></span>
