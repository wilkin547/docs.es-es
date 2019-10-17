---
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
ms.openlocfilehash: 2171b10d1c0eb7bcad894cc44c5103bdab18b0a5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395608"
---
# <a name="sqlstreamcharslength-property"></a><span data-ttu-id="34654-102">SqlStreamChars. length (propiedad)</span><span class="sxs-lookup"><span data-stu-id="34654-102">SqlStreamChars.Length Property</span></span>

<span data-ttu-id="34654-103">Cuando se reemplaza en una clase derivada, obtiene la longitud de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="34654-103">When overridden in a derived class, gets the length of the current stream.</span></span> <span data-ttu-id="34654-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="34654-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="34654-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34654-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="34654-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="34654-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="34654-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34654-107">Syntax</span></span>

```csharp
public abstract long Length { get; }
```

## <a name="property-value"></a><span data-ttu-id="34654-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="34654-108">Property value</span></span>

<xref:System.Int64>\
<span data-ttu-id="34654-109">Longitud de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="34654-109">The length of the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="34654-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34654-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="34654-111">La propiedad `SqlStreamChars.Length` es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="34654-111">The `SqlStreamChars.Length` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="34654-112">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="34654-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="34654-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34654-113">Requirements</span></span>

<span data-ttu-id="34654-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="34654-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="34654-115">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="34654-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="34654-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="34654-116">**.NET Framework versions:** Available since 2.0.</span></span>
