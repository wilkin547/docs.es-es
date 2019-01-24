---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 761ed0e30c6acca8c910c5dc97dfbae46c1f89bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564843"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase PeerSecuritySettings no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase PeerSecuritySettings tiene las siguientes propiedades:  
  
### <a name="mode"></a>Modo  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Si un punto de conexión configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.  
  
### <a name="transport"></a>Transporte  
 Tipo de datos: PeerTransportSecuritySettings  
  
 Tipo de acceso: De sólo lectura  
  
 Valores de seguridad de transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.PeerSecuritySettings>
