---
title: Clase de canal
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: a920636e7df9609b12834366b1488c80122f9fca
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274236"
---
# <a name="channel-class"></a>Clase de canal

Canal  
  
## <a name="syntax"></a>Syntax  
  
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

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 punto de conexión local para el canal.  
  
### <a name="ref"></a>ref  

 Tipo de datos: punto de conexión  
  
 Tipo de acceso: solo lectura  
  
 Una referencia al extremo al que se conecta el canal.  
  
### <a name="remoteaddress"></a>RemoteAddress  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Dirección remota asociada al canal.  
  
### <a name="sessionid"></a>SessionId  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Identificador de la sesión actual, si lo hubiera.  
  
### <a name="type"></a>Tipo  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El tipo de canal.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.ChannelBase>
