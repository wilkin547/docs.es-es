---
title: 'Cómo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 7e07e8d8781040d4ddc1d5643446f5a42354a557
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963547"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Cómo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET
Para configurar un punto de conexión de servicio de Windows Communication Foundation (WCF) para que sea interoperable con clientes de servicios Web de ASP.NET, use el tipo de <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como el tipo de enlace para el punto de conexión de servicio.  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace. Los clientes del servicio Web ASP.NET no admiten la codificación de mensajes MTOM, por lo que la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> se debe dejar como su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>. Los clientes de servicios web de ASP.NET no admiten WS-Security, por lo que la <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> debería estar establecida en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Para que los metadatos de un servicio WCF estén disponibles para las herramientas de generación de proxy del servicio Web de ASP.NET (es decir, la [herramienta lenguaje de descripción de servicios web (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100)), la [herramienta de detección de servicios web (disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))y la característica Agregar referencia Web en Visual Studio), debe exponer un extremo de metadatos HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Para agregar un punto de conexión de WCF que sea compatible con clientes del servicio web de ASP.NET mediante código  
  
1. Cree una nueva instancia de <xref:System.ServiceModel.BasicHttpBinding>  
  
2. De manera opcional, habilite la seguridad de transporte para este enlace de punto de conexión de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, consulte [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Agregue un nuevo extremo de la aplicación a su host de servicio mediante la instancia de enlace que acaba de crear. Para obtener más información sobre cómo agregar un punto de conexión de servicio en el código, vea [Cómo: crear un punto de conexión de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4. Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Para agregar un extremo WCF que sea compatible con clientes de servicio web de ASP.NET en un archivo de configuración  
  
1. Cree una nueva configuración de enlace <xref:System.ServiceModel.BasicHttpBinding>. Para obtener más información, consulte [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2. De manera opcional, habilite la seguridad de transporte para esta configuración de enlace de extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, vea [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Configure un nuevo punto de conexión de la aplicación para su servicio utilizando la configuración de enlace que acaba de crear. Para obtener más información sobre cómo agregar un punto de conexión de servicio en un archivo de configuración, consulte [Cómo: crear un punto de conexión de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Ejemplo  
 En el código de ejemplo siguiente se muestra cómo agregar un punto de conexión de WCF que es compatible con los clientes de servicios Web de ASP.NET en el código y, como alternativa, en los archivos de configuración.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a>Vea también

- [Creación de un punto de conexión de servicio en código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Publicación de metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Cómo especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Creación de un punto de conexión de servicio en configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Utilización de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)
