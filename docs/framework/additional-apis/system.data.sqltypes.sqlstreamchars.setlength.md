---
title: Método SqlStreamChars.SetLength(Int64) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 7eb2b1bfe0a3d180b54c41cbca1d645dfb402be7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152768"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="09d72-102">Método SqlStreamChars.SetLength(Int64)</span><span class="sxs-lookup"><span data-stu-id="09d72-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="09d72-103">Cuando se invalida en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="09d72-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="09d72-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="09d72-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="09d72-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09d72-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="09d72-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="09d72-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="09d72-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09d72-107">Parameters</span></span>

`value`\
<span data-ttu-id="09d72-108">Longitud deseada de la secuencia actual, en bytes.</span><span class="sxs-lookup"><span data-stu-id="09d72-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="09d72-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09d72-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="09d72-110">El `SqlStreamChars.SetLength` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="09d72-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="09d72-111">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="09d72-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="09d72-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09d72-112">Requirements</span></span>

<span data-ttu-id="09d72-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="09d72-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="09d72-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="09d72-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="09d72-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="09d72-115">**.NET Framework versions:** Available since 2.0.</span></span>