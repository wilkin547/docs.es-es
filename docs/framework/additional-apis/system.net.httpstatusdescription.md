---
description: 'Más información sobre: clase HttpStatusDescription'
title: Clase HttpStatusDescription (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fa135a6421397ce6b7be2af05d66aa8e81beafb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802507"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="3c30b-103">Clase HttpStatusDescription</span><span class="sxs-lookup"><span data-stu-id="3c30b-103">HttpStatusDescription class</span></span>

<span data-ttu-id="3c30b-104">Proporciona descripciones de Estado HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="3c30b-104">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="3c30b-105">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="3c30b-105">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="3c30b-106">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="3c30b-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="3c30b-107">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="3c30b-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="3c30b-108">método Get</span><span class="sxs-lookup"><span data-stu-id="3c30b-108">Get method</span></span>

<span data-ttu-id="3c30b-109">Devuelve la descripción asociada al código de Estado HTTP especificado.</span><span class="sxs-lookup"><span data-stu-id="3c30b-109">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="3c30b-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c30b-110">Parameters</span></span>

<span data-ttu-id="3c30b-111">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="3c30b-111">`code` <xref:System.Int32></span></span>

<span data-ttu-id="3c30b-112">El código de Estado HTTP, por ejemplo, `404` .</span><span class="sxs-lookup"><span data-stu-id="3c30b-112">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="3c30b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c30b-113">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="3c30b-114">La descripción del estado de HTTP.</span><span class="sxs-lookup"><span data-stu-id="3c30b-114">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c30b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c30b-115">Requirements</span></span>

<span data-ttu-id="3c30b-116">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="3c30b-116">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="3c30b-117">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="3c30b-117">**Assembly:** System (in System.dll)</span></span>
