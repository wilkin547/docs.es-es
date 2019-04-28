---
title: Propiedad SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlChars.Stream
- System.Data.SqlTypes.SqlChars.get_Stream
- System.Data.SqlTypes.SqlChars.set_Stream
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 4858d9f8878e5b56a0811edf92a2faa729775156
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675206"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="e6a53-102">Propiedad SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="e6a53-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="e6a53-103">Obtiene o establece la secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6a53-103">Gets or sets the character stream.</span></span> <span data-ttu-id="e6a53-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="e6a53-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="e6a53-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6a53-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="e6a53-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6a53-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="e6a53-107">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="e6a53-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="e6a53-108">La secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6a53-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6a53-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6a53-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e6a53-110">El `SqlChars.Stream` propiedad es interna y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="e6a53-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e6a53-111">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="e6a53-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6a53-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6a53-112">Requirements</span></span>

<span data-ttu-id="e6a53-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="e6a53-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="e6a53-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="e6a53-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="e6a53-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="e6a53-115">**.NET Framework versions:** Available since 2.0.</span></span>