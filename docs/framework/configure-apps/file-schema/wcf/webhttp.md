---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399159"
---
# \<webHttp>
Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración. Este comportamiento, cuando se usa junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar, habilita el modelo de programación web para un servicio de Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|automaticFormatSelectionEnabled|Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar. La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores. La selección de formato automática puede habilitarse mediante programación o a través de la configuración.|  
|defaultBodyStyle|Especifica el estilo de cuerpo predeterminado de los mensajes devueltos. Para obtener más información, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle> y el [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Especifica el formato de respuesta de salida predeterminado de los mensajes. Para obtener más información, consulte [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).|  
|helpEnabled|Obtiene o establece un valor que determina si la página de Ayuda está habilitada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica el conjunto de comportamientos del punto de conexión.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [Integración de AJAX y compatibilidad de JSON](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
