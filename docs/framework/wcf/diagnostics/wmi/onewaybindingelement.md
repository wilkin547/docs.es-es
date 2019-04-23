---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769273"
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase OneWayBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase OneWayBindingElement tiene las propiedades siguientes:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Tipo de datos: ChannelPoolSettings  
  
 Tipo de acceso: De sólo lectura  
  
 La configuración del grupo de canales.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de canales aceptados.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Valor que indica si el paquete se puede enrutar.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
