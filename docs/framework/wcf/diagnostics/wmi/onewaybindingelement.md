---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195819"
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
  
 Tipo de acceso: solo lectura  
  
 La configuración del grupo de canales.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de canales aceptados.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Valor que indica si el paquete se puede enrutar.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
