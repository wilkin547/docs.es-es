---
description: 'Más información sobre: WebHeaderCollection. AddInternal (método)'
title: Método WebHeaderCollection. AddInternal (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7bc84f84e6656dba5230b627fe9decfc4e0b4746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699485"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="3438b-103">WebHeaderCollection. AddInternal, método</span><span class="sxs-lookup"><span data-stu-id="3438b-103">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="3438b-104">Agrega un nuevo encabezado con el nombre y el valor especificados a la colección, omitiendo las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="3438b-104">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="3438b-105">Este método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="3438b-105">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3438b-106">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="3438b-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="3438b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3438b-107">Parameters</span></span>

- <span data-ttu-id="3438b-108">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="3438b-108">`name` <xref:System.String></span></span>

  <span data-ttu-id="3438b-109">Nombre del encabezado.</span><span class="sxs-lookup"><span data-stu-id="3438b-109">The name of the header.</span></span>

- <span data-ttu-id="3438b-110">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="3438b-110">`value` <xref:System.String></span></span>

  <span data-ttu-id="3438b-111">Valor del encabezado.</span><span class="sxs-lookup"><span data-stu-id="3438b-111">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="3438b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3438b-112">Requirements</span></span>

<span data-ttu-id="3438b-113">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3438b-113">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3438b-114">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="3438b-114">**Assembly:** System (in System.dll)</span></span>
