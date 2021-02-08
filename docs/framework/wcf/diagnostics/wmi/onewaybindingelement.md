---
description: 'Más información acerca de: OneWayBindingElement'
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 9c2ccc301bd854c7b85fcc53551ed6def329a8fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803092"
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

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
