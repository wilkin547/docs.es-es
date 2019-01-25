---
title: TcpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 33bbc1e5-44e4-4ee3-b7b5-801dc78956e4
ms.openlocfilehash: 0d5dc5c9b9bf2313d18c9fadb1a2adb87c1b11b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610791"
---
# <a name="tcptransportbindingelement"></a>TcpTransportBindingElement
TcpTransportBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class TcpTransportBindingElement : ConnectionOrientedTransportBindingElement  
{  
  TcpConnectionPoolSettings ConnectionPoolSettings;  
  sint32 ListenBacklog;  
  boolean PortSharingEnabled;  
  boolean TeredoEnabled;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TcpTransportBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TcpTransportBindingElement tiene las propiedades siguientes:  
  
### <a name="connectionpoolsettings"></a>connectionPoolSettings  
 Tipo de datos: TcpConnectionPoolSettings  
  
 Tipo de acceso: De sólo lectura  
  
 Agrupación de conexiones.  
  
### <a name="listenbacklog"></a>ListenBacklog  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de solicitudes de conexión en cola que pueden estar pendientes.  
  
### <a name="portsharingenabled"></a>PortSharingEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Valor booleano que especifica si el uso compartido de los puertos TCP está habilitado para esta conexión.  
  
### <a name="teredoenabled"></a>TeredoEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor booleano que especifica si Teredo (una tecnología para direccionar clientes que están detrás de firewalls) está habilitada.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
