---
title: "Cómo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ed4bf8e86e727505d48e85bb55a88452217c76b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Cómo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET
Para configurar un extremo de servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para que sea interoperable con clientes de servicios web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como el tipo de enlace de su extremo de servicio.  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace. Los clientes de servicios web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] no admiten la codificación de mensajes del MTOM, por lo que la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> debería quedar dejarse en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. Los clientes de servicios web de ASP.NET no admiten WS-Security, por lo que la <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> debería estar establecida en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Para que los metadatos una [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio disponible para [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] herramientas de generación de proxy de servicio Web (es decir, [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [(Web Services Discovery Tool Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)y la característica Agregar referencia Web en Visual Studio), debe exponer un extremo de metadatos HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Para agregar un punto de conexión de WCF que sea compatible con clientes del servicio web de ASP.NET mediante código  
  
1.  Cree una nueva instancia de <xref:System.ServiceModel.BasicHttpBinding>  
  
2.  De manera opcional, habilite la seguridad de transporte para este enlace de extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, vea [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Agregue un nuevo punto de conexión de la aplicación a su host de servicio mediante la instancia de enlace que acaba de crear. Para obtener más información sobre cómo agregar un extremo de servicio en el código, vea la [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Para agregar un punto de conexión WCF que sea compatible con clientes de servicio web de ASP.NET en un archivo de configuración  
  
1.  Cree una nueva configuración de enlace <xref:System.ServiceModel.BasicHttpBinding>. Para obtener más información, consulte el [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  De manera opcional, habilite la seguridad de transporte para esta configuración de enlace de extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, consulte [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Configure un nuevo punto de conexión de la aplicación para su servicio utilizando la configuración de enlace que acaba de crear. Para obtener más información sobre cómo agregar un extremo de servicio en un archivo de configuración, consulte la [Cómo: crear un extremo de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte el [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente muestra cómo agregar un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que es compatible con clientes de servicios Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en código y, alternativamente, en archivos de configuración.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Vea también  
 [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [Cómo: publicar los metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [Cómo especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Cómo: crear un extremo de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Cómo: publicar los metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Uso de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)
