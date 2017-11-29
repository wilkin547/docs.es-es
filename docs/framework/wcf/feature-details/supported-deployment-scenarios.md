---
title: "Escenarios de implementación admitidos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22dcace51b2c73193356450b4b210d1c1a899e28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="supported-deployment-scenarios"></a>Escenarios de implementación admitidos
El subconjunto de características de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admitido para su uso en aplicaciones de confianza parcial está diseñado para cumplir los requisitos de algunos, aunque no todos, escenarios de uso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. En el servidor, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cumple los requisitos de proveedores de hospedaje compartido de escala de Internet que ejecutan aplicaciones de terceros en el conjunto de permisos de Nivel de confianza medio [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] por razones de seguridad. En el cliente, la compatibilidad de confianza parcial de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está diseñada para cumplir los requisitos de tecnologías de implementación como [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) o la tecnología de aplicación de explorador XAML de [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)], que permiten una implementación perfecta y segura de aplicaciones de escritorio de los sitios que no son de confianza.  
  
## <a name="minimum-permission-requirements"></a>Requisitos mínimos de permiso  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite un subconjunto de características en aplicaciones que se ejecutan bajo cualquiera de los conjuntos de permisos con nombre estándares:  
  
-   Permisos de nivel de confianza medio  
  
-   Permisos de zona de Internet  
  
 Al intentar utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en aplicaciones parcialmente de confianza con permisos más restrictivos puede producir las excepciones de seguridad en el tiempo de ejecución.  
  
 Para obtener más información sobre las características admitidas en estos conjuntos de permisos, consulte [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Confianza parcial en el servidor  
 Muchos proveedores comerciales de servicios de hospedaje de aplicaciones web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] obligan a que las aplicaciones que se ejecutan en sus servidores se ejecuten en el conjunto de permisos Confianza media de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] . [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]pueden ejecutar servicios en estos entornos suponiendo que usen el <xref:System.ServiceModel.BasicHttpBinding>, el <xref:System.ServiceModel.WebHttpBinding>, o el <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> con seguridad de nivel de transporte.  
  
 Los servicios de[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan en entornos de hospedaje de Nivel de confianza medio también pueden actuar como servicios de nivel medio enviando mensajes a otros servidores en respuesta a solicitudes de cliente. Se admiten los escenarios de nivel medio en el servidor si el entorno de hospedaje ha concedido a la aplicación el <xref:System.Net.WebPermission> adecuado para realizar solicitudes salientes al servidor deseado.  
  
 Además del uso de uno de los enlaces SOAP admitidos por parte de la mensajería SOAP, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el <xref:System.ServiceModel.WebHttpBinding> para compilar servicios de estilo web en aplicaciones de confianza parcial. El [modelo de programación de Web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [sindicación en WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), y [integración de AJAX y compatibilidad de JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) características de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son compatibles con confianza parcial.  
  
 Los servicios de flujo requieren permisos de plena confianza y no se pueden utilizar en aplicaciones de confianza parcial.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Cómo: Usar el nivel de confianza medio en ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Confianza parcial en el Cliente  
 Se deben tomar ciertas precauciones de seguridad al descargar y ejecutar código desde sitios de Internet que no sean de confianza. Las tecnologías de [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) y de la aplicación de explorador XAML (XBAP) [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]hacen uso de la confianza parcial para conceder permisos limitados (zona de Internet) al código que no sea de confianza.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede usar para comunicarse con servidores remotos desde dentro de aplicaciones de confianza parcial implementadas mediante [ClickOnce Deployment](http://go.microsoft.com/fwlink/?LinkId=83712) o XBAP. El conjunto de permisos de la zona de Internet incluye la clase <xref:System.Net.WebPermission> para el host de origen, que permite a estas aplicaciones comunicarse con su servidor de origen mediante cualquiera de los enlaces admitidos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] descritos en [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad de acceso del código](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Información general sobre aplicaciones hospedadas en Explorador de Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [Confianza parcial](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Nivel de confianza medio de ASP.Net](http://go.microsoft.com/fwlink/?LinkId=69328)
