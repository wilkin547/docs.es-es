---
title: Procedimiento para configurar servicios WCF para interoperar con clientes de servicios web ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: ddd7e8c95701532010b54e5136a33d37d139f6a4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739230"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Procedimiento para configurar servicios WCF para interoperar con clientes de servicios web ASP.NET

Para configurar un extremo de servicio de Windows Communication Foundation (WCF) <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> para que sea interoperable con ASP.NET clientes de servicio web, use el tipo como tipo de enlace para el extremo de servicio.  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace. ASP.NET los clientes de servicio web no <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> admiten la codificación de <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>mensajes MTOM, por lo que la propiedad debe dejarse como su valor predeterminado, que es . ASP.NET clientes de servicio web no admiten WS-Security, por lo que <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> debe establecerse en . <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>  
  
 Para que los metadatos de un servicio WCF estén disponibles para ASP.NET herramientas de generación de proxy de servicio web (es decir, la herramienta de lenguaje de descripción de [servicios web (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100))la herramienta de detección de [servicios web (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))y la característica **Agregar referencia web** en Visual Studio), debe exponer un extremo de metadatos HTTP/GET.  
  
## <a name="add-an-endpoint-in-code"></a>Agregar un punto de conexión en el código  
  
1. Cree una nueva instancia de <xref:System.ServiceModel.BasicHttpBinding>  
  
2. De manera opcional, habilite la seguridad de transporte para este enlace de punto de conexión de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, consulte [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Agregue un nuevo extremo de la aplicación a su host de servicio mediante la instancia de enlace que acaba de crear. Para obtener más información sobre cómo agregar un punto de conexión de servicio en el código, vea [Cómo: crear un punto](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)de conexión de servicio en código .  
  
4. Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Agregar un punto de conexión en un archivo de configuración  
  
1. Cree una nueva configuración de enlace <xref:System.ServiceModel.BasicHttpBinding>. Para obtener más información, vea [Cómo: especificar un enlace](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)de servicio en la configuración .  
  
2. De manera opcional, habilite la seguridad de transporte para esta configuración de enlace de extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Para obtener más información, consulte [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Configure un nuevo punto de conexión de la aplicación para su servicio utilizando la configuración de enlace que acaba de crear. Para obtener más información sobre cómo agregar un punto de conexión de servicio en un archivo de configuración, consulte [Cómo: crear un punto](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)de conexión de servicio en la configuración .  
  
4. Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante un archivo](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)de configuración .  
  
## <a name="example"></a>Ejemplo  
 En el código de ejemplo siguiente se muestra cómo agregar un extremo WCF que es compatible con ASP.NET clientes de servicio web en código y, alternativamente, en archivos de configuración.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para crear un punto de conexión de servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Procedimiento para publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Procedimiento para especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Procedimiento para crear un punto de conexión de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Seguridad del transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Utilización de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)
