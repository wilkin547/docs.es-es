---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47de8c2449c46b12b8d10ac2a5269a18d1454f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
