---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 04e6abc5941ec99769ff2c15d47881b60e81d2e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048405"
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ConnectionOrientedTransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ConnectionOrientedTransportBindingElement tiene las propiedades siguientes:  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  
 Tipo de datos: datetime  
  
 Tipo de acceso: De sólo lectura  
  
 El timespan que especifica cuánto tiempo tiene la inicialización del canal para completarse antes de que se agote el tiempo de espera.  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El tamaño del búfer usado para transmitir un fragmento del mensaje serializado en la conexión del cliente o servicio.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor que indica si el nombre del host se usa para alcanzar el servicio al coincidir con el URI.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El tamaño máximo del búfer que se va a usar.  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  
 Tipo de datos: datetime  
  
 Tipo de acceso: De sólo lectura  
  
 El intervalo máximo de tiempo que un fragmento de un mensaje o un mensaje completo pueden estar almacenados en búfer en memoria antes de que se envíen.  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de subprocesos de aceptación asincrónica pendientes disponibles para procesar conexiones entrantes en el servicio.  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de conexiones pendientes.  
  
### <a name="transfermode"></a>TransferMode  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor que especifica si los mensajes están almacenados en búfer o se transmiten mediante el transporte orientado a la conexión.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
