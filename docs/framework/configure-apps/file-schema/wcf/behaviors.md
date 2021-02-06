---
description: 'Más información acerca de: <behaviors>'
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 3cb8edea76f6e7af3c3b387e5b04b89e58a28305
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639515"
---
# \<behaviors>

Este elemento define dos colecciones secundarias denominadas `endpointBehaviors` y `serviceBehaviors`.  Cada colección define los elementos de comportamiento utilizados respectivamente por extremos y servicios. Su atributo de `name` único identifica cada elemento de comportamiento. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Esta sección de configuración representa todos los comportamientos definidos para un extremo concreto.|  
|[\<serviceBehaviors>](servicebehaviors.md)|Esta sección de configuración representa todos los comportamientos definidos para un servicio concreto.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Observaciones  

 Puede usar el elemento `<remove>` para quitar un comportamiento determinado de la colección. Para ello, basta con proporcionar el nombre del comportamiento que se desea quitar en el atributo `name` del elemento `<remove>`.  También puede usar el elemento `<clear>` para asegurarse de que una colección de comportamientos se inicie vacía borrando todo el contenido de la colección.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [Configuración y extensión del tiempo de ejecución con comportamientos](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [Configuración de los comportamientos del cliente](../../../wcf/configuring-client-behaviors.md)
- [Especificación del comportamiento de tiempo de ejecución del cliente](../../../wcf/specifying-client-run-time-behavior.md)
- [Especificación del comportamiento en tiempo de ejecución del servicio](../../../wcf/specifying-service-run-time-behavior.md)
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
