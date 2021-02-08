---
description: 'Más información sobre: SqlStreamChars. CanSeek (propiedad)'
title: Propiedad SqlStreamChars. CanSeek (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5919a66bef9ac31e0ef15ad4af64b456700605f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802624"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="b4714-103">Propiedad SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="b4714-103">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="b4714-104">Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b4714-104">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="b4714-105">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="b4714-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="b4714-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4714-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="b4714-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="b4714-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="b4714-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="b4714-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="b4714-109">`true` Si la secuencia actual admite la operación de búsqueda; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="b4714-109">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4714-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4714-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b4714-111">La `SqlStreamChars.CanSeek` propiedad es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="b4714-111">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b4714-112">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="b4714-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4714-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4714-113">Requirements</span></span>

<span data-ttu-id="b4714-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="b4714-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="b4714-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="b4714-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="b4714-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="b4714-116">**.NET Framework versions:** Available since 2.0.</span></span>
