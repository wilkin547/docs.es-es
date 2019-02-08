---
title: Propiedad SqlChars.Stream (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology:
- dotnet-data
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
ms.openlocfilehash: 36a6b3f45f0832ed651dc0a613f50e7170517497
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827687"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="efe8e-102">Propiedad SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="efe8e-102">SqlChars.Stream Property</span></span>

<span data-ttu-id="efe8e-103">Obtiene o establece la secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="efe8e-103">Gets or sets the character stream.</span></span> <span data-ttu-id="efe8e-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="efe8e-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="efe8e-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="efe8e-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="efe8e-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="efe8e-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="efe8e-107">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="efe8e-107">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="efe8e-108">La secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="efe8e-108">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="efe8e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efe8e-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="efe8e-110">El `SqlChars.Stream` propiedad es interna y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="efe8e-110">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="efe8e-111">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="efe8e-111">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="efe8e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efe8e-112">Requirements</span></span>

<span data-ttu-id="efe8e-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="efe8e-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="efe8e-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="efe8e-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="efe8e-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="efe8e-115">**.NET Framework versions:** Available since 2.0.</span></span>