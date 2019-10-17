---
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
ms.openlocfilehash: 9c8a1526e75fdc304022e74a7cc52506762489ea
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395750"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="232a5-102">SqlStreamChars. Read (Char [], Int32, Int32) (método)</span><span class="sxs-lookup"><span data-stu-id="232a5-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="232a5-103">Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="232a5-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="232a5-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="232a5-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="232a5-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="232a5-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="232a5-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="232a5-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="232a5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="232a5-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="232a5-108">Matriz de caracteres que se va a leer.</span><span class="sxs-lookup"><span data-stu-id="232a5-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="232a5-109">Desplazamiento relativo al origen.</span><span class="sxs-lookup"><span data-stu-id="232a5-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="232a5-110">Número de caracteres que se van a leer de la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="232a5-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="232a5-111">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="232a5-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="232a5-112">Número total de caracteres leídos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="232a5-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="232a5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="232a5-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="232a5-114">El método `SqlStreamChars.Read` es privado y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="232a5-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="232a5-115">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="232a5-115">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="232a5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="232a5-116">Requirements</span></span>

<span data-ttu-id="232a5-117">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="232a5-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="232a5-118">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="232a5-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="232a5-119">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="232a5-119">**.NET Framework versions:** Available since 2.0.</span></span>
