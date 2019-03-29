---
title: Propiedad SqlStreamChars.IsNull (System.Data.SqlTypes)
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
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634341"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="f19b7-102">Propiedad SqlStreamChars.IsNull</span><span class="sxs-lookup"><span data-stu-id="f19b7-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="f19b7-103">Cuando se invalida en una clase derivada, obtiene un valor que indica si la secuencia es `null`.</span><span class="sxs-lookup"><span data-stu-id="f19b7-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="f19b7-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="f19b7-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f19b7-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f19b7-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f19b7-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="f19b7-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="f19b7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f19b7-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="f19b7-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="f19b7-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="f19b7-109">`true` Si la secuencia es `null`; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f19b7-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f19b7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f19b7-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f19b7-111">El `SqlStreamChars.IsNull` propiedad es privada y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="f19b7-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f19b7-112">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="f19b7-112">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f19b7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f19b7-113">Requirements</span></span>

<span data-ttu-id="f19b7-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f19b7-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f19b7-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="f19b7-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f19b7-116">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="f19b7-116">**.NET Framework versions:** Available since 2.0.</span></span>