---
title: Procedimiento para importar aserciones de directivas personalizadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
ms.openlocfilehash: fb5e3ba5faca1b32eef63ac174bcd7731ee50771
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249155"
---
# <a name="how-to-import-custom-policy-assertions"></a>Procedimiento para importar aserciones de directivas personalizadas

Las aserciones de directivas describen las funciones y requisitos de un extremo de servicio.  Las aplicaciones cliente pueden utilizar aserciones de directivas en metadatos del servicio para configurar el enlace de cliente o para personalizar el contrato de servicio de un punto de conexión de servicio.  
  
 Las aserciones de directiva personalizadas se importan implementando la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> y pasando ese objeto al sistema de los metadatos o registrando el tipo de implementación en su archivo de configuración de la aplicación.  Las implementaciones de la <xref:System.ServiceModel.Description.IPolicyImportExtension> interfaz deben proporcionar un constructor sin parámetros.  
  
### <a name="to-import-custom-policy-assertions"></a>Para importar aserciones de directivas personalizadas  
  
1. Implemente la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> en una clase. Consulte los procedimientos siguientes.  
  
2. Insertar el importador de directivas personalizadas mediante:  
  
3. El uso de un archivo de configuración Consulte los procedimientos siguientes.  
  
4. Usar un archivo de configuración con la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Consulte los procedimientos siguientes.  
  
5. Insertar mediante programación el importador de la directiva. Consulte los procedimientos siguientes.  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a>Para implementar la interfaz System.ServiceModel.Description.IPolicyImportExtension en cualquier clase  
  
1. En el método <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, para cada asunto de la directiva en la que esté interesado, busque las aserciones de directiva que desee importar llamando al método adecuado (dependiendo del ámbito de la aserción que desee) en el objeto <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> pasado al método. El ejemplo de código siguiente muestra cómo utilizar el método <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> para ubicar la aserción de directiva personalizada y quitarla de la colección en un paso. Si utiliza el método de eliminación para buscar y quitar la aserción, no tiene que realizar el paso 4.  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2. Procese las aserciones de directiva. Tenga en cuenta que el sistema de la directiva no normaliza directivas anidadas y `wsp:optional`. Debe procesar estas construcciones en su implementación de extensión de importación de directivas.  
  
3. Realice la personalización para el enlace o contrato que admite la función o el requisito especificó por la aserción de directiva. Normalmente las aserciones indican que un enlace requiere una configuración determinada o un elemento de enlace concreto. Realice estas modificaciones obteniendo acceso a la propiedad <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType>. Otras aserciones requieren que modifique el contrato.  Puede obtener acceso y modificar el contrato mediante la propiedad <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType>.  Observe que su importador de directivas se puede llamar varias veces para el mismo enlace y contrato, pero para alternativas de directivas diferentes si no se importa correctamente una alternativa de directivas. Su código debería ser resistente a este comportamiento.  
  
4. Elimine la aserción de directiva personalizada de la colección de aserciones. Si no quita la aserción Windows Communication Foundation (WCF) supone que la importación de la Directiva no se ha realizado correctamente y no importa el enlace asociado. Si usó el método <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> para ubicar la aserción de directivas personalizadas y eliminarla de la colección en un paso no tiene que realizar este paso.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a>Para insertar el importador de directivas personalizadas en el sistema de metadatos utilizando un archivo de configuración  
  
1. Agregue el tipo de importador al `<extensions>` elemento dentro del [\<policyImporters>](../../configure-apps/file-schema/wcf/policyimporters.md) elemento en el archivo de configuración del cliente.  
  
     [!code-xml[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]
  
2. En la aplicación cliente, utilice <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> para resolver los metadatos y se invoca automáticamente el importador.  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a>Para insertar el importador de directivas personalizadas en el sistema de metadatos utilizando Svcutil.exe  
  
1. Agregue el tipo de importador al `<extensions>` elemento dentro del [\<policyImporters>](../../configure-apps/file-schema/wcf/policyimporters.md) elemento en el archivo de configuración de Svcutil.exe.config. También puede señalar Svcutil.exe para cargar tipos de importador de directivas registrados en un archivo de configuración diferente mediante la opción `/svcutilConfig`.  
  
2. Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para importar los metadatos y el importador se invoca automáticamente.  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a>Para insertar mediante programación el importador de directivas personalizadas en el sistema de metadatos  
  
1. Agregue el importador a la propiedad <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType>(por ejemplo, si está utilizando ) <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> antes de importar los metadatos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>
- [Extensión del sistema de metadatos](extending-the-metadata-system.md)
