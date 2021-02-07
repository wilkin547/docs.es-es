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
# <a name="pooledstreamnetworkstream-property"></a>Propiedad PooledStream. NetworkStream

Obtiene o establece la secuencia de red para el `PooledStream` Socket.

## <a name="syntax"></a>Sintaxis

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Net.Sockets.NetworkStream>  
La secuencia de red para el `PooledStream` Socket.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> La `PooledStream.NetworkStream` propiedad es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System.dll)

**.NET Framework versiones:** Disponible desde 2,0.
