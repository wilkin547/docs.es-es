---
description: 'Más información sobre: propiedad PooledStream. NetworkStream'
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
ms.openlocfilehash: 8a4f1d6bd9297028e763ef73bf96f85cbbfdafd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699641"
---
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="4c6ba-103">Propiedad PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="4c6ba-103">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="4c6ba-104">Obtiene o establece la secuencia de red para el `PooledStream` Socket.</span><span class="sxs-lookup"><span data-stu-id="4c6ba-104">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="4c6ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c6ba-105">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="4c6ba-106">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="4c6ba-106">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="4c6ba-107">La secuencia de red para el `PooledStream` Socket.</span><span class="sxs-lookup"><span data-stu-id="4c6ba-107">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="4c6ba-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c6ba-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="4c6ba-109">La `PooledStream.NetworkStream` propiedad es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="4c6ba-109">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="4c6ba-110">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="4c6ba-110">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="4c6ba-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c6ba-111">Requirements</span></span>

<span data-ttu-id="4c6ba-112">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="4c6ba-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="4c6ba-113">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="4c6ba-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="4c6ba-114">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="4c6ba-114">**.NET Framework versions:** Available since 2.0.</span></span>
