---
title: Método SqlStreamChars. Flush (System. Data. SqlTypes)
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
ms.openlocfilehash: 38ade5ce38cfe5003b2d06c0d8bb2db1a20bc05b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395625"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="4664a-102">SqlStreamChars. Flush (método)</span><span class="sxs-lookup"><span data-stu-id="4664a-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="4664a-103">Cuando se reemplaza en una clase derivada, borra todos los búferes de esta secuencia y hace que todos los datos almacenados en el búfer se escriban en el dispositivo subyacente.</span><span class="sxs-lookup"><span data-stu-id="4664a-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="4664a-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="4664a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="4664a-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4664a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="4664a-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="4664a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="4664a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4664a-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="4664a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4664a-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4664a-109">El método `SqlStreamChars.Flush` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="4664a-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4664a-110">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="4664a-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4664a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4664a-111">Requirements</span></span>

<span data-ttu-id="4664a-112">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="4664a-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="4664a-113">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="4664a-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="4664a-114">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="4664a-114">**.NET Framework versions:** Available since 2.0.</span></span>
