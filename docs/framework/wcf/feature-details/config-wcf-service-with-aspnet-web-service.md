---
title: "C&#243;mo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# C&#243;mo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET
Para configurar un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extremo de servicio para poder interoperar con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] clientes de servicios Web, use la <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> que el tipo de enlace para el extremo de servicio.  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Clientes de servicios Web no admiten la codificación de mensajes MTOM, por lo que la <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> propiedad debe dejarse como su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName>. Los clientes de servicios Web de ASP.Net son compatibles con WS-Security, por lo que la <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> debe establecerse en <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
 Para hacer que los metadatos de un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio disponible para [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] herramientas de generación de proxy de servicio Web (es decir, [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [herramienta descubrimiento de servicios Web (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)y la característica Agregar referencia Web en Visual Studio), debe exponer un extremo de metadatos HTTP/GET.  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a>Para agregar un punto de conexión de WCF que sea compatible con clientes del servicio web de ASP.NET mediante código  
  
1.  Crear un nuevo <xref:System.ServiceModel.BasicHttpBinding> instancia  
  
2.  Opcionalmente, habilitar la seguridad de transporte para este enlace de extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode>. Para obtener más información, consulte [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Agregue un nuevo punto de conexión de la aplicación a su host de servicio mediante la instancia de enlace que acaba de crear. Para obtener más información sobre cómo agregar un extremo de servicio en el código, consulte el [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).  
  
4.  Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte [Cómo: Publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a>Para agregar un punto de conexión WCF que sea compatible con clientes de servicio web de ASP.NET en un archivo de configuración  
  
1.  Crear un nuevo <xref:System.ServiceModel.BasicHttpBinding> configuración de enlace. Para obtener más información, consulte el [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
2.  Habilitar opcionalmente la seguridad de transporte para esta configuración de enlace del extremo de servicio estableciendo el modo de seguridad para el enlace en <xref:System.ServiceModel.BasicHttpSecurityMode>. Para obtener más información, consulte [seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3.  Configure un nuevo punto de conexión de la aplicación para su servicio utilizando la configuración de enlace que acaba de crear. Para obtener más información sobre cómo agregar un extremo de servicio en un archivo de configuración, consulte la [Cómo: crear un extremo de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
4.  Habilite un punto de conexión de metadatos HTTP/GET para su servicio. Para obtener más información, consulte el [Cómo: Publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente muestra cómo agregar un extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que es compatible con clientes de servicios Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] en código y, alternativamente, en archivos de configuración.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Cómo: crear un extremo de servicio en el código](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)   
 [Cómo: Publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)   
 [Cómo: especificar un enlace de servicio en la configuración](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)   
 [Cómo: crear un extremo de servicio en la configuración](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)   
 [Cómo: publicar los metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Seguridad de transporte](../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Uso de metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)