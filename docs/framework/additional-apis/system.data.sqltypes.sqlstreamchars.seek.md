---
title: Método SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
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
ms.openlocfilehash: 6b69f87da9fb3829d765dc135de1f6c10765b63a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634357"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="ae45a-102">Método SqlStreamChars.Seek (Int64, SeekOrigin)</span><span class="sxs-lookup"><span data-stu-id="ae45a-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="ae45a-103">Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="ae45a-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="ae45a-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="ae45a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="ae45a-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae45a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="ae45a-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="ae45a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="ae45a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae45a-107">Parameters</span></span>

`offset`\
<span data-ttu-id="ae45a-108">Desplazamiento de bytes relativo a `origin`.</span><span class="sxs-lookup"><span data-stu-id="ae45a-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="ae45a-109">Uno de los valores de enumeración que indica el punto de referencia desde el que se va a obtener la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="ae45a-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="ae45a-110">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="ae45a-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="ae45a-111">La nueva posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="ae45a-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae45a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae45a-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ae45a-113">El `SqlStreamChars.Seek` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="ae45a-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ae45a-114">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ae45a-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ae45a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae45a-115">Requirements</span></span>

<span data-ttu-id="ae45a-116">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="ae45a-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="ae45a-117">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="ae45a-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="ae45a-118">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="ae45a-118">**.NET Framework versions:** Available since 2.0.</span></span>
