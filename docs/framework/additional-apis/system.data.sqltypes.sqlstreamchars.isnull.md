---
description: 'Más información sobre: SqlStreamChars. IsNull (propiedad)'
title: Propiedad SqlStreamChars. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b1408a8ba9cd1c38f73d5fa6b818f441d6223bc8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791925"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="45bd5-103">SqlStreamChars. IsNull (propiedad)</span><span class="sxs-lookup"><span data-stu-id="45bd5-103">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="45bd5-104">Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia es `null` .</span><span class="sxs-lookup"><span data-stu-id="45bd5-104">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="45bd5-105">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="45bd5-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="45bd5-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45bd5-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="45bd5-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="45bd5-107">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="45bd5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45bd5-108">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="45bd5-109">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="45bd5-109">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="45bd5-110">`true` Si la secuencia es `null` ; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="45bd5-110">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="45bd5-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45bd5-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="45bd5-112">La `SqlStreamChars.IsNull` propiedad es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="45bd5-112">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="45bd5-113">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="45bd5-113">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="45bd5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45bd5-114">Requirements</span></span>

<span data-ttu-id="45bd5-115">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="45bd5-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="45bd5-116">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="45bd5-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="45bd5-117">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="45bd5-117">**.NET Framework versions:** Available since 2.0.</span></span>
