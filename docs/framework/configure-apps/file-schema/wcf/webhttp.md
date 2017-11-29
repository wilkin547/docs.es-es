---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c51c8ac43549994752999db08dbb92d43bc7a86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebhttpgt"></a>&lt;webHttp&gt;
Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un extremo a través de la configuración. Este comportamiento, cuando se usa junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, permite que el modelo de programación Web para un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] servicio.  
  
 \<sistema. ServiceModel >  
\<comportamientos >  
\<endpointBehaviors >  
\<comportamiento >  
\<webHttp >  
  
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
|defaultBodyStyle|Especifica el estilo de cuerpo predeterminado de los mensajes devueltos. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Web.WebMessageBodyStyle> y [Web HTTP de WCF formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|defaultOutgoingResponseFormat|Especifica el formato de respuesta de salida predeterminado de los mensajes. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Web HTTP de WCF formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).|  
|faultExceptionEnabled|Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).|  
|helpEnabled|Obtiene o establece un valor que determina si la página de Ayuda está habilitada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el conjunto de comportamientos del punto de conexión.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [Integración de AJAX y compatibilidad de JSON](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
