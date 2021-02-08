---
description: 'Más información sobre: SqlStreamChars. Read (Char [], Int32, Int32) (método)'
title: Método SqlStreamChars. Read (Char [], Int32, Int32) (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/20/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: a899ddff7b7242fcc32aaf7b7f7794970596027b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802585"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="065ae-103">SqlStreamChars. Read (Char [], Int32, Int32) (método)</span><span class="sxs-lookup"><span data-stu-id="065ae-103">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="065ae-104">Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="065ae-104">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="065ae-105">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="065ae-105">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="065ae-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="065ae-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="065ae-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="065ae-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="065ae-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="065ae-108">Parameters</span></span>

`buffer`\
<span data-ttu-id="065ae-109">Matriz de caracteres que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="065ae-109">A char array to read.</span></span>

`offset`\
<span data-ttu-id="065ae-110">Desplazamiento relativo al origen.</span><span class="sxs-lookup"><span data-stu-id="065ae-110">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="065ae-111">Número de caracteres que se van a leer de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="065ae-111">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="065ae-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="065ae-112">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="065ae-113">Número total de caracteres leídos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="065ae-113">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="065ae-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="065ae-114">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="065ae-115">El `SqlStreamChars.Read` método es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="065ae-115">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="065ae-116">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="065ae-116">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="065ae-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="065ae-117">Requirements</span></span>

<span data-ttu-id="065ae-118">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="065ae-118">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="065ae-119">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="065ae-119">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="065ae-120">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="065ae-120">**.NET Framework versions:** Available since 2.0.</span></span>
