---
description: 'Más información sobre: SqlStreamChars. Write (Char [], Int32, Int32) (método)'
title: Método SqlStreamChars. Write (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 3031b57902215df01c5c30625281a99be73ba2d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802559"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="3bacc-103">SqlStreamChars. Write (Char [], Int32, Int32) (método)</span><span class="sxs-lookup"><span data-stu-id="3bacc-103">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="3bacc-104">Cuando se reemplaza en una clase derivada, escribe una secuencia de caracteres en la secuencia actual y avanza la posición actual dentro de la secuencia según el número de caracteres escritos.</span><span class="sxs-lookup"><span data-stu-id="3bacc-104">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="3bacc-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="3bacc-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="3bacc-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3bacc-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="3bacc-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="3bacc-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="3bacc-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bacc-108">Parameters</span></span>

`buffer`  
<span data-ttu-id="3bacc-109">Matriz de caracteres que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="3bacc-109">A char array to write.</span></span>

`offset`  
<span data-ttu-id="3bacc-110">Desplazamiento relativo al origen.</span><span class="sxs-lookup"><span data-stu-id="3bacc-110">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="3bacc-111">Número de caracteres que se van a escribir en la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="3bacc-111">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bacc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bacc-112">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="3bacc-113">El `SqlStreamChars.Write` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="3bacc-113">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3bacc-114">Microsoft no admite el uso de este método de escritura en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="3bacc-114">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bacc-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bacc-115">Requirements</span></span>

<span data-ttu-id="3bacc-116">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="3bacc-116">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="3bacc-117">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="3bacc-117">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="3bacc-118">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="3bacc-118">**.NET Framework versions:** Available since 2.0.</span></span>
