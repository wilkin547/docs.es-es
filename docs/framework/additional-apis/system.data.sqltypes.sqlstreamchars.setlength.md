---
title: Método SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 750b46c2050228f630eaa6be31922869bff15e0a
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827349"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="ff481-102">Método SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="ff481-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="ff481-103">Cuando se invalida en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ff481-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="ff481-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="ff481-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="ff481-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ff481-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="ff481-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="ff481-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="ff481-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff481-107">Parameters</span></span>

`value`\
<span data-ttu-id="ff481-108">Longitud deseada de la secuencia actual, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ff481-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff481-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff481-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ff481-110">El `SqlStreamChars.SetLength` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="ff481-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ff481-111">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="ff481-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff481-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff481-112">Requirements</span></span>

<span data-ttu-id="ff481-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="ff481-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="ff481-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="ff481-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="ff481-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="ff481-115">**.NET Framework versions:** Available since 2.0.</span></span>