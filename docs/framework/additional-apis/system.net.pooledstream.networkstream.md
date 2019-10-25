---
title: Propiedad PooledStream. NetworkStream (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847233"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="26ebf-102">Propiedad PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="26ebf-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="26ebf-103">Obtiene o establece la secuencia de red para el socket `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="26ebf-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="26ebf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26ebf-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="26ebf-105">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="26ebf-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="26ebf-106">La secuencia de red para el socket de `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="26ebf-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="26ebf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26ebf-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="26ebf-108">La propiedad `PooledStream.NetworkStream` es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="26ebf-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="26ebf-109">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="26ebf-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="26ebf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26ebf-110">Requirements</span></span>

<span data-ttu-id="26ebf-111">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="26ebf-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="26ebf-112">**Ensamblado:** Sistema (en System. dll)</span><span class="sxs-lookup"><span data-stu-id="26ebf-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="26ebf-113">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="26ebf-113">**.NET Framework versions:** Available since 2.0.</span></span>
