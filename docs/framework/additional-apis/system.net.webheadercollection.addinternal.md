---
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
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990494"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="737bb-102">WebHeaderCollection. AddInternal, método</span><span class="sxs-lookup"><span data-stu-id="737bb-102">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="737bb-103">Agrega un nuevo encabezado con el nombre y el valor especificados a la colección, omitiendo las comprobaciones.</span><span class="sxs-lookup"><span data-stu-id="737bb-103">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="737bb-104">Este método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="737bb-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="737bb-105">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="737bb-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="737bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="737bb-106">Parameters</span></span>

- <span data-ttu-id="737bb-107">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="737bb-107">`name` <xref:System.String></span></span>

  <span data-ttu-id="737bb-108">Nombre del encabezado.</span><span class="sxs-lookup"><span data-stu-id="737bb-108">The name of the header.</span></span>

- <span data-ttu-id="737bb-109">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="737bb-109">`value` <xref:System.String></span></span>

  <span data-ttu-id="737bb-110">Valor del encabezado.</span><span class="sxs-lookup"><span data-stu-id="737bb-110">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="737bb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="737bb-111">Requirements</span></span>

<span data-ttu-id="737bb-112">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="737bb-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="737bb-113">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="737bb-113">**Assembly:** System (in System.dll)</span></span>
