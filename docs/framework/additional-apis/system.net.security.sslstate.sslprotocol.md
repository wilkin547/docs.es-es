---
description: 'Más información sobre: SslState. SslProtocol (propiedad)'
title: Propiedad SslState. SslProtocol (System .net. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: b0b9bebf23fcd8d643d06f1cff10c260c77a7c08
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699628"
---
# <a name="sslstatesslprotocol-property"></a>Propiedad SslState. SslProtocol

Obtiene las versiones del protocolo SSL.

## <a name="syntax"></a>Sintaxis

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>Valor de propiedad

<xref:System.Security.Authentication.SslProtocols>  
Combinación bit a bit de los valores de enumeración que especifican las versiones del protocolo SSL.

## <a name="remarks"></a>Observaciones

> [!WARNING]
> La `SslState.SslProtocol` propiedad es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net.Security>

**Ensamblado:** Sistema (en System.dll)

**.NET Framework versiones:** Disponible desde 2,0.
