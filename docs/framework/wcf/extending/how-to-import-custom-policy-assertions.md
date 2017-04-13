---
title: "C&#243;mo: Importar aserciones de directivas personalizadas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Importar aserciones de directivas personalizadas
Las aserciones de directivas describen las funciones y requisitos de un punto de conexión de servicio.  Las aplicaciones cliente pueden utilizar aserciones de directivas en metadatos del servicio para configurar el enlace de cliente o para personalizar el contrato de servicio de un punto de conexión de servicio.  
  
 Aserciones de directiva personalizadas se importan implementando la <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> interfaz y pasando ese objeto en el sistema de metadatos o registrando la implementación del tipo en el archivo de configuración de la aplicación.  Las implementaciones de la <xref:System.ServiceModel.Description.IPolicyImportExtension> interfaz debe proporcionar un constructor predeterminado.  
  
### <a name="to-import-custom-policy-assertions"></a>Para importar aserciones de directivas personalizadas  
  
1.  Implemente el <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> interfaz en una clase. Consulte los procedimientos siguientes.  
  
2.  Insertar el importador de directivas personalizadas mediante:  
  
3.  El uso de un archivo de configuración Consulte los procedimientos siguientes.  
  
4.  Utilizar un archivo de configuración [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Consulte los procedimientos siguientes.  
  
5.  Insertar mediante programación el importador de la directiva. Consulte los procedimientos siguientes.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>Para implementar la interfaz System.ServiceModel.Description.IPolicyImportExtension en cualquier clase  
  
1.  En el <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=fullName> (método), para cada asunto de directiva que le interesa, busque las aserciones de directiva que desee importar llamando al método adecuado (dependiendo del ámbito de la aserción que desee) en el <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName> objeto pasado al método. En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> método para ubicar la aserción de directiva personalizada y quitarla de la colección en un solo paso. Si utiliza el método de eliminación para buscar y quitar la aserción, no tiene que realizar el paso 4.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  Procese las aserciones de directiva. Tenga en cuenta que el sistema de la directiva no normaliza directivas anidadas y `wsp:optional`. Debe procesar estas construcciones en su implementación de extensión de importación de directivas.  
  
3.  Realice la personalización para el enlace o contrato que admite la función o el requisito especificó por la aserción de directiva. Normalmente las aserciones indican que un enlace requiere una configuración determinada o un elemento de enlace concreto. Realice estas modificaciones obteniendo acceso a la <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=fullName> propiedad. Otras aserciones requieren que modifique el contrato.  Puede acceder y modificar el contrato mediante el <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=fullName> propiedad.  Observe que su importador de directivas se puede llamar varias veces para el mismo enlace y contrato, pero para alternativas de directivas diferentes si no se importa correctamente una alternativa de directivas. Su código debería ser resistente a este comportamiento.  
  
4.  Elimine la aserción de directiva personalizada de la colección de aserciones. Si no elimina la aserción, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supone que la importación de la directiva no se realizó correctamente y no importa el enlace asociado. Si ha usado la <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=fullName> método para ubicar la aserción de directiva personalizada y quitarla de la colección en un paso no es necesario realizar este paso.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>Para insertar el importador de directivas personalizadas en el sistema de metadatos utilizando un archivo de configuración  
  
1.  Agregar el tipo de importador el `<extensions>` elemento dentro de la [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) el elemento en el archivo de configuración de cliente.  
  
     [!code[CustomPolicySample#7](../../../../samples/snippets/common/VS_Snippets_CFX/custompolicysample/common/client.exe.config#7)]
     [!code-csharp[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]
     [!code-vb[CustomPolicySample#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.exe.config#7)]  
  
2.  En la aplicación cliente, utilice la <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName> o <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName> para resolver los metadatos y el importador se invoca automáticamente.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>Para insertar el importador de directivas personalizadas en el sistema de metadatos utilizando Svcutil.exe  
  
1.  Agregar el tipo de importador el `<extensions>` elemento dentro de la [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) el elemento en el archivo de configuración Svcutil.exe.config. También puede señalar Svcutil.exe para cargar tipos de importador de directivas registrados en un archivo de configuración diferente mediante la opción `/svcutilConfig`.  
  
2.  Utilice [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) importar los metadatos y el importador se invoca automáticamente.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>Para insertar mediante programación el importador de directivas personalizadas en el sistema de metadatos  
  
1.  Agregue el importador a la <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=fullName> propiedad (por ejemplo, si usa el <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>) antes de importar los metadatos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=fullName>   
 [Extender el sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)