---
title: Propiedad SmiOrderProperty.Item (Microsoft.SqlServer.Server)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- Microsoft.SqlServer.Server.SmiOrderProperty.Item
- Microsoft.SqlServer.Server.SmiOrderProperty.get_Item
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 5453167e16e2658b3546b7114201b04d481a0c79
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "54223019"
---
# <a name="smiorderpropertyitem-property"></a><span data-ttu-id="bfae1-102">Propiedad SmiOrderProperty.Item</span><span class="sxs-lookup"><span data-stu-id="bfae1-102">SmiOrderProperty.Item Property</span></span>

<span data-ttu-id="bfae1-103">Obtiene el orden de las columnas de la entidad.</span><span class="sxs-lookup"><span data-stu-id="bfae1-103">Gets the column order for the entity.</span></span> <span data-ttu-id="bfae1-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="bfae1-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="bfae1-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bfae1-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="bfae1-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="bfae1-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfae1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfae1-107">Syntax</span></span>

```csharp
internal SmiColumnOrder Item { get; }
```

## <a name="property-value"></a><span data-ttu-id="bfae1-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="bfae1-108">Property value</span></span>

<span data-ttu-id="bfae1-109">El orden de las columnas.</span><span class="sxs-lookup"><span data-stu-id="bfae1-109">The column order.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfae1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfae1-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="bfae1-111">El `SmiOrderProperty.Item` propiedad es interna y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="bfae1-111">The `SmiOrderProperty.Item` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="bfae1-112">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="bfae1-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="bfae1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfae1-113">Requirements</span></span>

<span data-ttu-id="bfae1-114">**Espacio de nombres:** <xref:Microsoft.SqlServer.Server></span><span class="sxs-lookup"><span data-stu-id="bfae1-114">**Namespace:** <xref:Microsoft.SqlServer.Server></span></span>

<span data-ttu-id="bfae1-115">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="bfae1-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="bfae1-116">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="bfae1-116">**.NET Framework versions:** Available since 2.0.</span></span>