---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
