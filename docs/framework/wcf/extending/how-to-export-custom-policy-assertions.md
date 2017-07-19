---
title: "C&#243;mo: Exportar aserciones de directivas personalizadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# C&#243;mo: Exportar aserciones de directivas personalizadas
Las aserciones de directivas describen las funciones y requisitos de un extremo de servicio.Las aplicaciones de servicio pueden utilizar las aserciones de directivas personalizadas en metadatos del servicio para comunicarse el extremo, enlace o información de personalización de contrato a la aplicación cliente.Puede utilizar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para exportar las aserciones en expresiones de directivas adjuntas a enlaces de WSDL en el extremo, operación o asuntos del mensaje, dependiendo de las funciones o requisitos que esté comunicando.  
  
 Las aserciones de directivas personalizadas se exportan implementando la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> en <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> e insertando directamente el elemento de enlace en el enlace del extremo de servicio o registrando el elemento de enlace en su archivo de configuración de la aplicación.Su implementación de exportación de directivas debería agregar su aserción de directivas personalizada como una instancia <xref:System.Xml.XmlElement?displayProperty=fullName> al <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=fullName> adecuado en <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName> que se pasa al método <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>.  
  
 Además, debe comprobar la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> de la clase <xref:System.ServiceModel.Description.WsdlExporter> y exportar expresiones de directivas anidadas y atributos de marco de directivas en el espacio de nombres correcto basándose en la versión de directiva especificada.  
  
 Para importar las aserciones de directivas personalizadas, vea <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> y [Cómo: Importar aserciones de directivas personalizadas](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).  
  
### Para exportar aserciones de directivas personalizadas  
  
1.  Implemente la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> en <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>.El ejemplo de código siguiente muestra la implementación de una aserción de directiva personalizada en el nivel de enlace.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2.  Inserte el elemento de enlace en el enlace del extremo mediante programación o utilizando un archivo de configuración de la aplicación.Consulte los procedimientos siguientes.  
  
### Para insertar un elemento de enlace mediante un archivo de configuración de la aplicación  
  
1.  Implemente <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=fullName> para su elemento de enlace de la aserción de directiva personalizada.  
  
2.  Agregue la extensión del elemento de enlace al archivo de configuración utilizando el elemento [\<bindingElementExtensions\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md).  
  
3.  Cree un enlace personalizado mediante <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.  
  
### Para insertar un elemento de enlace mediante programación  
  
1.  Cree un nuevo <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> y agréguelo a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.  
  
2.  Agregue el enlace personalizado del paso 1.a un nuevo extremo y agregue ese nuevo extremo de servicio a <xref:System.ServiceModel.ServiceHost?displayProperty=fullName> llamando al método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
3.  Abra <xref:System.ServiceModel.ServiceHost>.El ejemplo de código siguiente muestra la creación de un enlace personalizado y la inserción mediante programación de elementos de enlace.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## Vea también  
 <xref:System.ServiceModel.Description.IPolicyImportExtension>   
 <xref:System.ServiceModel.Description.IPolicyExportExtension>   
 [Cómo: Importar aserciones de directivas personalizadas](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)