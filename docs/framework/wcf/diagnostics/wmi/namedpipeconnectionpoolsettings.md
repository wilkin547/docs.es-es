---
description: 'Más información acerca de: NamedPipeConnectionPoolSettings'
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 8d724c7a24f62a8d48797125528eb8a194ece660
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803118"
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings

NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Métodos  

 La clase NamedPipeConnectionPoolSettings no define ningún método.  
  
## <a name="properties"></a>Propiedades  

 La clase NamedPipeConnectionPoolSettings tiene las siguientes propiedades:  
  
### <a name="groupname"></a>NombreDeGrupo  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre del grupo de conexiones utilizado por el elemento de enlace.  
  
### <a name="idletimeout"></a>IdleTimeout  

 Tipo de datos: datetime  
  
 Tipo de acceso: solo lectura  
  
 El tiempo máximo que la conexión puede estar inactiva antes de desconectarse.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de conexiones salientes para cada punto de conexión en el cliente.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
