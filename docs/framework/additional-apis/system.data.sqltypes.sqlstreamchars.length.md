---
title: Propiedad SqlStreamChars.Length (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 1ee15641e697a9d5d146f921640c73ff84a5c335
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152718"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="cc242-102">Propiedad SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="cc242-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="cc242-103">Cuando se invalida en una clase derivada, obtiene la longitud de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="cc242-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="cc242-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="cc242-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="cc242-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc242-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="cc242-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc242-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc242-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc242-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="cc242-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="cc242-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="cc242-109">Longitud de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="cc242-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc242-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc242-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="cc242-111">El `SqlStreamChars.Length` propiedad es privada y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="cc242-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cc242-112">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="cc242-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc242-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc242-113">Requirements</span></span>

<span data-ttu-id="cc242-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="cc242-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="cc242-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="cc242-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="cc242-116">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="cc242-116">**.NET Framework versions:** Available since 2.0.</span></span>