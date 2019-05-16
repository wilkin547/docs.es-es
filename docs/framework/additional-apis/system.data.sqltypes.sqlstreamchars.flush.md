---
title: Método SqlStreamChars.Flush (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 411bd0036de904dd485d9fb54fa5fd45e3b55dbb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634333"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="8a8a4-102">Método SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="8a8a4-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="8a8a4-103">Cuando se reemplaza en una clase derivada, borra todos los búferes de esta secuencia y hace que todos los datos almacenados en el búfer se escriban en el dispositivo subyacente.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="8a8a4-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="8a8a4-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="8a8a4-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a8a4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a8a4-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="8a8a4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a8a4-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="8a8a4-109">El `SqlStreamChars.Flush` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8a8a4-110">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a8a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a8a4-111">Requirements</span></span>

<span data-ttu-id="8a8a4-112">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="8a8a4-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="8a8a4-113">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="8a8a4-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="8a8a4-114">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="8a8a4-114">**.NET Framework versions:** Available since 2.0.</span></span>
