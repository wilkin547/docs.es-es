---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 2de417e4a4f5c6197551c1408da6907e2fa7c635
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269007"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings

PeerSecuritySettings  
  
## <a name="syntax"></a>Syntax  
  
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
  
### <a name="mode"></a>Mode  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Si un extremo configurado con el enlace emplea la seguridad del nivel de mensaje o de transporte.  
  
### <a name="transport"></a>Transporte  

 Tipo de datos: PeerTransportSecuritySettings  
  
 Tipo de acceso: solo lectura  
  
 Valores de seguridad de transporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.PeerSecuritySettings>
