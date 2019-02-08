---
title: Método SqlStreamChars.Write (Char [], Int32, Int32) (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: e2b0d2c4e68ffa0c0b9e745a15dbb8c79659008c
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826036"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="4742a-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span><span class="sxs-lookup"><span data-stu-id="4742a-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="4742a-103">Cuando se invalida en una clase derivada, escribe una secuencia de caracteres en la secuencia actual y avanza la posición actual dentro de la secuencia según el número de caracteres escritos.</span><span class="sxs-lookup"><span data-stu-id="4742a-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="4742a-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="4742a-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="4742a-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4742a-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="4742a-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="4742a-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="4742a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4742a-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="4742a-108">Para escribir una matriz de char.</span><span class="sxs-lookup"><span data-stu-id="4742a-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="4742a-109">Un desplazamiento con respecto al origen.</span><span class="sxs-lookup"><span data-stu-id="4742a-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="4742a-110">El número de caracteres que se escribirá en la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="4742a-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="4742a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4742a-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4742a-112">El `SqlStreamChars.Write` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="4742a-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4742a-113">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="4742a-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4742a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4742a-114">Requirements</span></span>

<span data-ttu-id="4742a-115">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="4742a-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="4742a-116">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="4742a-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="4742a-117">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="4742a-117">**.NET Framework versions:** Available since 2.0.</span></span>