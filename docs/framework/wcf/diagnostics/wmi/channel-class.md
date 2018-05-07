---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 4b7c66560c0c136a258c527d8a681d491eb50aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="channel-class"></a>Clase de canal
Canal  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase Canal no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase Canal tiene las propiedades siguientes.  
  
### <a name="localaddress"></a>LocalAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Extremo local para el canal.  
  
### <a name="ref"></a>ref  
 Tipo de datos: extremo  
  
 Tipo de acceso: solo lectura  
  
 Una referencia al extremo al que se conecta el canal.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Dirección remota asociada al canal.  
  
### <a name="sessionid"></a>SessionId  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Identificador de la sesión actual, si lo hubiera.  
  
### <a name="type"></a>Tipo  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El tipo de canal.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.ChannelBase>
