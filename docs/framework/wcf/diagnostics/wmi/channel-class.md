---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 3fbf398cca7ae9adbbecb9439bf3cbd32eb03969
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668397"
---
# <a name="channel-class"></a>Clase de canal
Canal  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
  
 Tipo de acceso: De sólo lectura  
  
 punto de conexión local para el canal.  
  
### <a name="ref"></a>ref  
 Tipo de datos: punto de conexión  
  
 Tipo de acceso: De sólo lectura  
  
 Una referencia al punto de conexión al que se conecta el canal.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Dirección remota asociada al canal.  
  
### <a name="sessionid"></a>SessionId  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Identificador de la sesión actual, si lo hubiera.  
  
### <a name="type"></a>Tipo  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El tipo de canal.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.ChannelBase>
