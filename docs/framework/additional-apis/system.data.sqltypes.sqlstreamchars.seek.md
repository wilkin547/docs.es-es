---
description: 'Más información sobre: SqlStreamChars. Seek (Int64, SeekOrigin) (método)'
title: Método SqlStreamChars. Seek (Int64, SeekOrigin) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 00f71aff95045d566b7932aec3f7e18259b4dfa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802572"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="46c08-103">SqlStreamChars. Seek (Int64, SeekOrigin) (método)</span><span class="sxs-lookup"><span data-stu-id="46c08-103">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="46c08-104">Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="46c08-104">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="46c08-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="46c08-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="46c08-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46c08-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="46c08-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="46c08-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="46c08-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46c08-108">Parameters</span></span>

`offset`\
<span data-ttu-id="46c08-109">Desplazamiento de bytes relacionado con `origin`.</span><span class="sxs-lookup"><span data-stu-id="46c08-109">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="46c08-110">Uno de los valores de enumeración que indica el punto de referencia del que se va a obtener la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="46c08-110">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="46c08-111">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="46c08-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="46c08-112">La nueva posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="46c08-112">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="46c08-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46c08-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="46c08-114">El `SqlStreamChars.Seek` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="46c08-114">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="46c08-115">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="46c08-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="46c08-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46c08-116">Requirements</span></span>

<span data-ttu-id="46c08-117">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="46c08-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="46c08-118">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="46c08-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="46c08-119">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="46c08-119">**.NET Framework versions:** Available since 2.0.</span></span>
