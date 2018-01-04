---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25893b1f3cf6cf20ae674bade5090a70c5f381a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
