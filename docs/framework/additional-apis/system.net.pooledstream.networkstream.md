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
# <a name="pooledstreamnetworkstream-property"></a>Propiedad PooledStream. NetworkStream

Obtiene o establece la secuencia de red para el socket `PooledStream`.

## <a name="syntax"></a>Sintaxis

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Net.Sockets.NetworkStream>  
La secuencia de red para el socket de `PooledStream`.

## <a name="remarks"></a>Comentarios

> [!WARNING]
> La propiedad `PooledStream.NetworkStream` es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net>

**Ensamblado:** Sistema (en System. dll)

**.NET Framework versiones:** Disponible desde 2,0.
