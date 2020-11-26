---
title: Procedimiento para exportar aserciones de directivas personalizadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
ms.openlocfilehash: 8bdc9948d6846631fde1d428c113682f40d15ec3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249220"
---
# <a name="how-to-export-custom-policy-assertions"></a>Procedimiento para exportar aserciones de directivas personalizadas

Las aserciones de directivas describen las funciones y requisitos de un extremo de servicio. Las aplicaciones de servicio pueden utilizar las aserciones de directivas personalizadas en metadatos del servicio para comunicarse el extremo, enlace o información de personalización de contrato a la aplicación cliente. Puede usar Windows Communication Foundation (WCF) para exportar aserciones en expresiones de directiva adjuntas a los enlaces de WSDL en el extremo, la operación o los asuntos del mensaje, en función de las capacidades o los requisitos que se están comunicando.  
  
 Las aserciones de directivas personalizadas se exportan implementando la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> en <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> e insertando directamente el elemento de enlace en el enlace del punto de conexión de servicio o registrando el elemento de enlace en su archivo de configuración de la aplicación. Su implementación de exportación de directivas debería agregar su aserción de directivas personalizada como una instancia <xref:System.Xml.XmlElement?displayProperty=nameWithType> al <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType> adecuado en <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> que se pasa al método <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>.  
  
 Además, debe comprobar la propiedad <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> de la clase <xref:System.ServiceModel.Description.WsdlExporter> y exportar expresiones de directivas anidadas y atributos de marco de directivas en el espacio de nombres correcto basándose en la versión de directiva especificada.  
  
 Para importar aserciones de directivas personalizadas, vea <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> y [Cómo: importar aserciones de directivas personalizadas](how-to-import-custom-policy-assertions.md).  
  
### <a name="to-export-custom-policy-assertions"></a>Para exportar aserciones de directivas personalizadas  
  
1. Implemente la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> en <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>. El ejemplo de código siguiente muestra la implementación de una aserción de directiva personalizada en el nivel de enlace.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2. Inserte el elemento de enlace en el enlace del punto de conexión mediante programación o utilizando un archivo de configuración de la aplicación. Consulte los procedimientos siguientes.  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a>Para insertar un elemento de enlace mediante un archivo de configuración de la aplicación  
  
1. Implemente <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> para su elemento de enlace de la aserción de directiva personalizada.  
  
2. Agregue la extensión de elemento de enlace al archivo de configuración mediante el [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) elemento.  
  
3. Cree un enlace personalizado mediante <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.  
  
### <a name="to-insert-a-binding-element-programmatically"></a>Para insertar un elemento de enlace mediante programación  
  
1. Cree un nuevo <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> y agréguelo a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.  
  
2. Agregue el enlace personalizado del paso 1. a un nuevo punto de conexión y agregue ese nuevo punto de conexión de servicio a <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> llamando al método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  
  
3. Abra <xref:System.ServiceModel.ServiceHost>. El ejemplo de código siguiente muestra la creación de un enlace personalizado y la inserción mediante programación de elementos de enlace.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.IPolicyImportExtension>
- <xref:System.ServiceModel.Description.IPolicyExportExtension>
- [Procedimiento para importar aserciones de directivas personalizadas](how-to-import-custom-policy-assertions.md)
