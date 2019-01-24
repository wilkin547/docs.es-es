---
title: ChannelPoolSettings
ms.date: 03/30/2017
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
ms.openlocfilehash: 4a3e45140765f99f4a30b77fc9d02b167601b50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591489"
---
# <a name="channelpoolsettings"></a>ChannelPoolSettings
ChannelPoolSettings  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ChannelPoolSettings no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ChannelPoolSettings tiene las propiedades siguientes:  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: De sólo lectura  
  
 El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: De sólo lectura  
  
 El tiempo máximo para que la operación de concesión se complete antes de que se agote el tiempo de espera.  
  
### <a name="maxoutboundchannelsperendpoint"></a>MaxOutboundChannelsPerEndpoint  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de canales de salida para cada punto de conexión.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
