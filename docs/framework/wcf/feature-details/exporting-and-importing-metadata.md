---
title: Exportación e importación de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], exporting and importing
ms.assetid: 614a75bb-e0b0-4c95-b6d8-02cb5e5ddb38
ms.openlocfilehash: f07a1a10529aa1615bb00a0f3faeca9cb249aa64
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595536"
---
# <a name="exporting-and-importing-metadata"></a>Exportación e importación de metadatos
En Windows Communication Foundation (WCF), la exportación de metadatos es el proceso de describir puntos de conexión de servicio y proyectarlos en una representación paralela y estandarizada que pueden usar los clientes para entender cómo utilizar el servicio. Importar los metadatos de servicio es el proceso de generar instancias de <xref:System.ServiceModel.Description.ServiceEndpoint> o partes de los metadatos de servicio.  
  
## <a name="exporting-metadata"></a>Exportación de metadatos  
 Para exportar metadatos desde instancias de <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>, utilice una implementación de la clase abstracta <xref:System.ServiceModel.Description.MetadataExporter>. El <xref:System.ServiceModel.Description.WsdlExporter> tipo es la implementación de la <xref:System.ServiceModel.Description.MetadataExporter> clase abstracta incluida con WCF.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> genera los metadatos del Lenguaje de descripción de servicios Web (WSDL) con expresiones de directiva adjuntas encapsuladas en una instancia de <xref:System.ServiceModel.Description.MetadataSet>. Puede utilizar una instancia <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> para exportar de manera iterativa metadatos para los objetos <xref:System.ServiceModel.Description.ContractDescription> y  <xref:System.ServiceModel.Description.ServiceEndpoint>. Puede exportar también una colección de objetos <xref:System.ServiceModel.Description.ServiceEndpoint> y asociarlos a un nombre de servicios concreto.  
  
> [!NOTE]
> `WsdlExporter` solo puede utilizarse para exportar los metadatos desde las instancias `ContractDescription` que contienen el tipo de información Common Language Runtime (CLR), como, por ejemplo, una instancia de `ContractDescription` creada mediante el método `ContractDescription.GetContract`, o como parte de `ServiceDescription` de una instancia `ServiceHost`. No puede utilizar `WsdlExporter` para exportar metadatos a partir de las instancias `ContractDescription` importadas desde los metadatos del servicio o construidas sin información del tipo.  
  
## <a name="importing-metadata"></a>Importación de metadatos  
  
### <a name="importing-wsdl-documents"></a>Importación de documentos WSDL  
 Para importar metadatos de servicio en WCF, use una implementación de la <xref:System.ServiceModel.Description.MetadataImporter> clase abstracta. El <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> tipo es la implementación de la <xref:System.ServiceModel.Description.MetadataImporter> clase abstracta incluida con WCF. El tipo <xref:System.ServiceModel.Description.WsdlImporter> importa metadatos de WSDL con directivas adjuntas empaquetadas en un objeto <xref:System.ServiceModel.Description.MetadataSet>.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlImporter> le da control sobre cómo importar los metadatos. Puede importar todos los puntos de conexión, todos los enlaces o todos los contratos. Puede importar todos los puntos de conexión asociados a un servicio específico de WSDL, enlace o tipo de puerto. También puede importar el extremo de un puerto WSDL concreto, el enlace para un enlace de WSDL concreto o el contrato para un tipo de puerto de WSDL concreto.  
  
 <xref:System.ServiceModel.Description.WsdlImporter> también expone una propiedad <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A> que le permite especificar un conjunto de contratos que no necesita ser importado. <xref:System.ServiceModel.Description.WsdlImporter> utiliza los contratos en la propiedad <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A> en lugar de importar un contrato con el mismo nombre completo de los metadatos.  
  
### <a name="importing-policies"></a>Importación de directivas  
 El tipo <xref:System.ServiceModel.Description.WsdlImporter> recoge las expresiones de directivas adjuntas al mensaje, operación y los sujetos de directiva del punto de conexión y, a continuación, utiliza las implementaciones <xref:System.ServiceModel.Description.IPolicyImportExtension> en la colección <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> para importar las expresiones de directiva.  
  
 La lógica de importación de directiva administra automáticamente las referencias de directivas a las expresiones de directivas en el mismo documento WSDL y se identifica con un atributo `wsu:Id` o `xml:id`. La lógica de importación de directiva protege las aplicaciones frente a las referencias de directivas circulares, limitando el tamaño de una expresión de directiva a 4.096 nodos, donde un nodo es uno de los elementos siguientes: `wsp:Policy`, `wsp:All`, `wsp:ExactlyOne`, `wsp:policyReference`.  
  
 La lógica de importación de directiva normaliza también automáticamente las expresiones de directivas. No se normalizan las expresiones de directiva anidadas ni el atributo `wsp:Optional`. La cantidad de procesamiento de normalización realizado se limita a 4.096 pasos, donde cada paso produce una aserción de directiva, o un elemento secundario de un elemento `wsp:ExactlyOne`.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlImporter> prueba hasta 32 combinaciones de alternativas de directivas adjuntas a los distintos sujetos de directivas de WSDL. Si ninguna combinación se importa limpiamente, la primera combinación se utiliza para construir un enlace personalizado parcial.  
  
## <a name="error-handling"></a>Tratamiento de errores  
 Tanto el tipo <xref:System.ServiceModel.Description.MetadataExporter> como <xref:System.ServiceModel.Description.MetadataImporter> exponen una propiedad `Errors` que puede contener una colección de mensajes de error y advertencia encontrados durante los procesos de exportación e importación respectivamente, que se puede utilizar al implementar las herramientas.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlImporter> generalmente produce una excepción para una excepción detectada durante el proceso de importación y agrega un error correspondiente a su propiedad `Errors`. Los métodos <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A>y <xref:System.ServiceModel.Description.WsdlImporter.ImportEndpoints%2A> sin embargo, no producen estas excepciones, por lo que debe comprobar la propiedad `Errors` para determinar si se produjo algún problema al llamar a estos métodos.  
  
 El tipo vuelve a producir <xref:System.ServiceModel.Description.WsdlExporter> cualquier excepción detectada durante el proceso de exportación. Estas excepciones no se capturan como errores en la propiedad `Errors`. Cuando <xref:System.ServiceModel.Description.WsdlExporter> produce una excepción, está en un estado de error y no se puede reutilizar. <xref:System.ServiceModel.Description.WsdlExporter> agrega advertencias a su propiedad `Errors` cuando no se puede exportar una operación porque utiliza acciones de carácter comodín y cuando se encuentran nombres de enlace duplicados.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimiento para importar metadatos a puntos de conexión de servicio](how-to-import-metadata-into-service-endpoints.md)  
 Describe cómo importar los metadatos descargados en objetos de descripción.  
  
 [Procedimiento para exportar metadatos desde puntos de conexión de servicio](how-to-export-metadata-from-service-endpoints.md)  
 Describe cómo exportar objetos de descripción en metadatos.  
  
 [ServiceDescription y referencias WSDL](servicedescription-and-wsdl-reference.md)  
 Describe la asignación entre los objetos de descripción y WSDL.  
  
 [Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)  
 Describe el uso de Svcutil.exe para exportar metadatos para los servicios, contratos y tipos de datos en ensamblados compilados.  
  
 [Referencia de esquema de contrato de datos](data-contract-schema-reference.md)  
 Describe el subconjunto del esquema XML (XSD) utilizado por <xref:System.Runtime.Serialization.DataContractSerializer> para describir los tipos de Common Language Runtime (CLR) para la serialización XML.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Description.WsdlExporter>  
  
 <xref:System.ServiceModel.Description.WsdlImporter>  
  
## <a name="see-also"></a>Vea también

- [Exportación de metadatos personalizados para una extensión WCF](../extending/exporting-custom-metadata-for-a-wcf-extension.md)
- [Importación de  metadatos personalizados para una extensión de WCF](../extending/importing-custom-metadata-for-a-wcf-extension.md)
