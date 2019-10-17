---
title: Método SqlStreamChars. SetLength (Int64) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.SetLength
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 291d6e9395581f2370dafc728521a314d54a686d
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395721"
---
# <a name="sqlstreamcharssetlengthint64-method"></a><span data-ttu-id="9365a-102">SqlStreamChars. SetLength (Int64) (método)</span><span class="sxs-lookup"><span data-stu-id="9365a-102">SqlStreamChars.SetLength(Int64) Method</span></span>

<span data-ttu-id="9365a-103">Cuando se reemplaza en una clase derivada, libera los recursos utilizados por la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9365a-103">When overridden in a derived class, releases the resources used by the stream.</span></span> <span data-ttu-id="9365a-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="9365a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="9365a-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9365a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="9365a-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="9365a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void SetLength (long value);
```

## <a name="parameters"></a><span data-ttu-id="9365a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9365a-107">Parameters</span></span>

`value`\
<span data-ttu-id="9365a-108">Longitud deseada de la secuencia actual, en bytes.</span><span class="sxs-lookup"><span data-stu-id="9365a-108">The desired length of the current stream in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="9365a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9365a-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="9365a-110">El método `SqlStreamChars.SetLength` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="9365a-110">The `SqlStreamChars.SetLength` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="9365a-111">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="9365a-111">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9365a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9365a-112">Requirements</span></span>

<span data-ttu-id="9365a-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="9365a-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="9365a-114">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="9365a-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="9365a-115">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="9365a-115">**.NET Framework versions:** Available since 2.0.</span></span>
