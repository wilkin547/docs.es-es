---
title: Método SqlStreamChars.Flush (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Flush
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ecaf7932a4e832a88b883ceac4746afe6140b38e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152748"
---
# <a name="sqlstreamcharsflush-method"></a><span data-ttu-id="f383b-102">Método SqlStreamChars.Flush</span><span class="sxs-lookup"><span data-stu-id="f383b-102">SqlStreamChars.Flush Method</span></span>

<span data-ttu-id="f383b-103">Cuando se reemplaza en una clase derivada, borra todos los búferes de esta secuencia y hace que todos los datos almacenados en el búfer se escriban en el dispositivo subyacente.</span><span class="sxs-lookup"><span data-stu-id="f383b-103">When overridden in a derived class, clears all buffers for this stream and causes any buffered data to be written to the underlying device.</span></span> <span data-ttu-id="f383b-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="f383b-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="f383b-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f383b-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="f383b-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="f383b-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="f383b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f383b-107">Syntax</span></span>

```csharp
public abstract void Flush ();
```

## <a name="remarks"></a><span data-ttu-id="f383b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f383b-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f383b-109">El `SqlStreamChars.Flush` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="f383b-109">The `SqlStreamChars.Flush` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f383b-110">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="f383b-110">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f383b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f383b-111">Requirements</span></span>

<span data-ttu-id="f383b-112">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="f383b-112">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="f383b-113">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="f383b-113">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="f383b-114">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="f383b-114">**.NET Framework versions:** Available since 2.0.</span></span>