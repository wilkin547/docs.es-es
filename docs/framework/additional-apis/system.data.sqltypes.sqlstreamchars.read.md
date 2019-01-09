---
title: Método SqlStreamChars.Read (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152538"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="2b2b8-102">Método SqlStreamChars.Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="2b2b8-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="2b2b8-103">Cuando se invalida en una clase derivada, lee el siguiente conjunto de caracteres del flujo de entrada.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="2b2b8-104">El ensamblado que contiene este método tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="2b2b8-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="2b2b8-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="2b2b8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b2b8-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="2b2b8-108">Una matriz de caracteres para leer.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="2b2b8-109">Un desplazamiento con respecto al origen.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="2b2b8-110">El número de caracteres que leer en la secuencia actual.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="2b2b8-111">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="2b2b8-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="2b2b8-112">Número total de caracteres leídos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b2b8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b2b8-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="2b2b8-114">El `SqlStreamChars.Read` método es privado y no está pensado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="2b2b8-115">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="2b2b8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b2b8-116">Requirements</span></span>

<span data-ttu-id="2b2b8-117">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="2b2b8-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="2b2b8-118">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="2b2b8-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="2b2b8-119">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="2b2b8-119">**.NET Framework versions:** Available since 2.0.</span></span>