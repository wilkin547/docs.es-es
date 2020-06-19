---
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
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990515"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="0a874-102">Clase HttpStatusDescription</span><span class="sxs-lookup"><span data-stu-id="0a874-102">HttpStatusDescription class</span></span>

<span data-ttu-id="0a874-103">Proporciona descripciones de Estado HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="0a874-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="0a874-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="0a874-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="0a874-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0a874-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0a874-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0a874-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="0a874-107">método Get</span><span class="sxs-lookup"><span data-stu-id="0a874-107">Get method</span></span>

<span data-ttu-id="0a874-108">Devuelve la descripción asociada al código de Estado HTTP especificado.</span><span class="sxs-lookup"><span data-stu-id="0a874-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="0a874-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a874-109">Parameters</span></span>

<span data-ttu-id="0a874-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="0a874-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="0a874-111">El código de Estado HTTP, por ejemplo, `404` .</span><span class="sxs-lookup"><span data-stu-id="0a874-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="0a874-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a874-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="0a874-113">La descripción del estado de HTTP.</span><span class="sxs-lookup"><span data-stu-id="0a874-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a874-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a874-114">Requirements</span></span>

<span data-ttu-id="0a874-115">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0a874-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0a874-116">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="0a874-116">**Assembly:** System (in System.dll)</span></span>
