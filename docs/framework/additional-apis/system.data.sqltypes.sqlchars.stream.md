---
description: 'Más información sobre: SqlChars. Stream (propiedad)'
title: Propiedad SqlChars. Stream (System. Data. SqlTypes)
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
ms.openlocfilehash: 9af0df98b268a749d890ab1b40dddbbe98ced8d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802650"
---
# <a name="sqlcharsstream-property"></a><span data-ttu-id="78081-103">Propiedad SqlChars.Stream</span><span class="sxs-lookup"><span data-stu-id="78081-103">SqlChars.Stream Property</span></span>

<span data-ttu-id="78081-104">Obtiene o establece la secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="78081-104">Gets or sets the character stream.</span></span> <span data-ttu-id="78081-105">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="78081-105">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="78081-106">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="78081-106">It's intended for use by SQL Server.</span></span> <span data-ttu-id="78081-107">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="78081-107">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
internal SqlStreamChars Stream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="78081-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="78081-108">Property value</span></span>

`System.Data.SqlTypes.SqlStreamChars`\
<span data-ttu-id="78081-109">El flujo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="78081-109">The character stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="78081-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78081-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="78081-111">La `SqlChars.Stream` propiedad es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="78081-111">The `SqlChars.Stream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="78081-112">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="78081-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="78081-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78081-113">Requirements</span></span>

<span data-ttu-id="78081-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="78081-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="78081-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="78081-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="78081-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="78081-116">**.NET Framework versions:** Available since 2.0.</span></span>
