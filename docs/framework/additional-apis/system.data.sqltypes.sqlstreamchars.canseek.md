---
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
ms.openlocfilehash: eb32978f62b7d46f0abf715e2bca347592c0fda8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395776"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="c0365-102">Propiedad SqlStreamChars. CanSeek</span><span class="sxs-lookup"><span data-stu-id="c0365-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="c0365-103">Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c0365-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="c0365-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="c0365-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c0365-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0365-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c0365-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="c0365-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="c0365-107">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="c0365-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="c0365-108">`true` si la secuencia actual admite la operación de búsqueda; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c0365-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0365-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0365-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c0365-110">La propiedad `SqlStreamChars.CanSeek` es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="c0365-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c0365-111">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="c0365-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0365-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0365-112">Requirements</span></span>

<span data-ttu-id="c0365-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c0365-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c0365-114">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="c0365-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c0365-115">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="c0365-115">**.NET Framework versions:** Available since 2.0.</span></span>
