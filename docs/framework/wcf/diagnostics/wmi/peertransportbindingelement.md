---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 68e6a25e4e3f47c556363e2fd5aa8d3bb9946449
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485650"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
 Tipo de acceso: solo lectura  
  
 La dirección IP en la que el nodo del mismo nivel realiza escuchas para los mensajes.  
  
### <a name="port"></a>Puerto  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El puerto de la interfaz de red en el que este enlace procesa los mensajes del canal del mismo nivel.  
  
### <a name="security"></a>Seguridad  
 Tipo de datos: PeerSecuritySettings  
  
 Tipo de acceso: solo lectura  
  
 Valores de seguridad de transporte del mismo nivel.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
