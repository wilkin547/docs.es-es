---
title: Método SqlStreamChars.Seek (Int64, SeekOrigin) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Seek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: aab3195ec0d300a7f001f98f2d646c85be939356
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152558"
---
# <a name="sqlstreamcharsseekint64-seekorigin-method"></a><span data-ttu-id="20db6-102">Método SqlStreamChars.Seek (Int64, SeekOrigin)</span><span class="sxs-lookup"><span data-stu-id="20db6-102">SqlStreamChars.Seek(Int64, SeekOrigin) Method</span></span>

<span data-ttu-id="20db6-103">Cuando se reemplaza en una clase derivada, se establece la posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="20db6-103">When overridden in a derived class, sets the position within the current stream.</span></span> <span data-ttu-id="20db6-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="20db6-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="20db6-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="20db6-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="20db6-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="20db6-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract long Seek (long offset, System.IO.SeekOrigin origin);
```

## <a name="parameters"></a><span data-ttu-id="20db6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20db6-107">Parameters</span></span>

`offset`\
<span data-ttu-id="20db6-108">Desplazamiento de bytes relativo a `origin`.</span><span class="sxs-lookup"><span data-stu-id="20db6-108">A byte offset relative to `origin`.</span></span>

`origin`\
<span data-ttu-id="20db6-109">Uno de los valores de enumeración que indica el punto de referencia desde el que se va a obtener la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="20db6-109">One of the enumeration values that indicates the reference point from which to obtain the new position.</span></span>

## <a name="returns"></a><span data-ttu-id="20db6-110">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="20db6-110">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="20db6-111">La nueva posición dentro de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="20db6-111">The new position within the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="20db6-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20db6-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="20db6-113">El `SqlStreamChars.Seek` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="20db6-113">The `SqlStreamChars.Seek` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="20db6-114">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="20db6-114">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="20db6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20db6-115">Requirements</span></span>

<span data-ttu-id="20db6-116">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="20db6-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="20db6-117">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="20db6-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="20db6-118">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="20db6-118">**.NET Framework versions:** Available since 2.0.</span></span>