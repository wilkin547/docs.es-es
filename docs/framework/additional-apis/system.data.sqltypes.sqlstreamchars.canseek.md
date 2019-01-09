---
title: Propiedad SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 0145fe87e2c8aa3dd40e73f0089fe40b6b6cca30
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152738"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="c5cb3-102">Propiedad SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="c5cb3-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="c5cb3-103">Cuando se invalida en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="c5cb3-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="c5cb3-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="c5cb3-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="c5cb3-107">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="c5cb3-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="c5cb3-108">`true` Si la secuencia actual admite la operación de búsqueda; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5cb3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5cb3-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c5cb3-110">El `SqlStreamChars.CanSeek` propiedad es privada y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c5cb3-111">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c5cb3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5cb3-112">Requirements</span></span>

<span data-ttu-id="c5cb3-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="c5cb3-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="c5cb3-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="c5cb3-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="c5cb3-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="c5cb3-115">**.NET Framework versions:** Available since 2.0.</span></span>