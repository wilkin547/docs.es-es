---
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
ms.openlocfilehash: 9d952041122ceb3824712bd81cab7ce4789c9db8
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395586"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="68076-102">SqlStreamChars. Write (Char [], Int32, Int32) (método)</span><span class="sxs-lookup"><span data-stu-id="68076-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="68076-103">Cuando se reemplaza en una clase derivada, escribe una secuencia de caracteres en la secuencia actual y avanza la posición actual dentro de la secuencia según el número de caracteres escritos.</span><span class="sxs-lookup"><span data-stu-id="68076-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="68076-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="68076-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="68076-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68076-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="68076-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="68076-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="68076-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68076-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="68076-108">Matriz de caracteres que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="68076-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="68076-109">Desplazamiento relativo al origen.</span><span class="sxs-lookup"><span data-stu-id="68076-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="68076-110">Número de caracteres que se van a escribir en la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="68076-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="68076-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68076-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="68076-112">El método `SqlStreamChars.Write` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="68076-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="68076-113">Microsoft no admite el uso de este método de escritura en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="68076-113">Microsoft does not support the use of this method write in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="68076-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68076-114">Requirements</span></span>

<span data-ttu-id="68076-115">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="68076-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="68076-116">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="68076-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="68076-117">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="68076-117">**.NET Framework versions:** Available since 2.0.</span></span>
