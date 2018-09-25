---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: c74ee82d7aa3a23f0ee6a69185ad45857c31bb0b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087884"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
 Tipo de acceso: solo lectura  
  
 Si un punto de conexión configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.  
  
### <a name="transport"></a>Transporte  
 Tipo de datos: PeerTransportSecuritySettings  
  
 Tipo de acceso: solo lectura  
  
 Valores de seguridad de transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.PeerSecuritySettings>
