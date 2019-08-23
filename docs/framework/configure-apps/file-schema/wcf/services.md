---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937200"
---
# <a name="services"></a>\<> de servicios
Los servicios se definen en la sección de `services` del archivo de configuración. Cada servicio tiene su propia sección de configuración de `service`.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<service>](service.md)|Defina el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServicesSection>
