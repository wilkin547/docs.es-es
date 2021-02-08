---
description: 'Más información acerca de: PeerSecuritySettings'
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: a8b5b8c88e71cb46110fa35186599c0f9c366d17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803014"
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
