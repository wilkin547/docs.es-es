---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194076"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase PeerTransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase PeerTransportBindingElement tiene las propiedades siguientes:  
  
### <a name="listenipaddress"></a>ListenIPAddress  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.  
  
### <a name="port"></a>Puerto  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.  
  
### <a name="security"></a>Seguridad  
 Tipo de datos: PeerSecuritySettings  
  
 Tipo de acceso: De sólo lectura  
  
 Valores de seguridad de transporte del mismo nivel.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
