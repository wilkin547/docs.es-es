---
title: Propiedad SqlStreamChars.Length (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/19/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Length
- System.Data.SqlTypes.SqlStreamChars.get_Length
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ac6e6af9c9411ebc25039e0992133fae2b35ee23
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221186"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="a71f0-102">Propiedad SqlStreamChars.Length</span><span class="sxs-lookup"><span data-stu-id="a71f0-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="a71f0-103">Cuando se invalida en una clase derivada, obtiene la longitud de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="a71f0-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="a71f0-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="a71f0-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="a71f0-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a71f0-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="a71f0-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="a71f0-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="a71f0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a71f0-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="a71f0-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="a71f0-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="a71f0-109">Longitud de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a71f0-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="a71f0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a71f0-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a71f0-111">El `SqlStreamChars.Length` propiedad es privada y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="a71f0-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a71f0-112">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="a71f0-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a71f0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a71f0-113">Requirements</span></span>

<span data-ttu-id="a71f0-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="a71f0-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="a71f0-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="a71f0-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="a71f0-116">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="a71f0-116">**.NET Framework versions:** Available since 2.0.</span></span>