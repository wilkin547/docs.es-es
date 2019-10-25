---
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
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847251"
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

## <a name="remarks"></a>Comentarios

> [!WARNING]
> La propiedad `SslState.SslProtocol` es interna y no está diseñada para usarse directamente en el código.
>
> Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.

## <a name="requirements"></a>Requisitos

**Espacio de nombres:** <xref:System.Net.Security>

**Ensamblado:** Sistema (en System. dll)

**.NET Framework versiones:** Disponible desde 2,0.
