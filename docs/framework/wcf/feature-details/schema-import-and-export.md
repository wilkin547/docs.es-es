---
title: "Importaci&#243;n y exportaci&#243;n de esquemas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, importación y exportación de esquemas"
  - "Clase XsdDataContractExporter "
  - "Clase XsdDataContractImporter"
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Importaci&#243;n y exportaci&#243;n de esquemas
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]incluye un nuevo motor de serialización, el <xref:System.Runtime.Serialization.DataContractSerializer>. `DataContractSerializer` traduce entre los objetos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y XML (en ambas direcciones). Además del propio serializador, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye la importación del esquema asociado y los mecanismos de exportación de esquema. *Esquema* es una descripción formal, exacta y legible de la forma del XML que el serializador genera o que puede tener acceso el deserializador. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el Lenguaje de definición de esquemas (XSD) XML de World Wide Web Consortium (W3C) como su representación de esquema, que es muy interoperable con numerosas plataformas de terceros.  
  
 El componente de importación de esquema <xref:System.Runtime.Serialization.XsdDataContractImporter>, toma un documento de esquema XSD y genera [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] clases (normalmente las clases de contrato de datos) de manera que los formularios serializados se corresponden con el esquema dado.  
  
 Por ejemplo, el fragmento de esquema siguiente:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 genera el tipo siguiente (simplificado ligeramente para una mejor interpretación).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Tenga en cuenta que el tipo generado sigue varios procedimientos recomendados contrato de datos (se encuentra en [prácticas recomendadas: versiones de contratos de datos](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
-   El tipo implementa la <xref:System.Runtime.Serialization.IExtensibleDataObject> interfaz. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Contratos de datos compatibles con el reenvío](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
-   Los miembros de datos se implementan como propiedades públicas que se ajustan a los campos privados.  
  
-   La clase es una clase parcial y se pueden realizar adiciones sin modificar el código generado.  
  
 El <xref:System.Runtime.Serialization.XsdDataContractExporter> le permite hacer lo contrario: tomar los tipos que son serializables con el `DataContractSerializer` y generar un documento de esquema XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>La fidelidad no está garantizada  
 No se garantiza que el esquema o los tipos realicen un viaje de ida y vuelta (round trip) con fidelidad total. (Un *ida y vuelta* significa importar un esquema para crear un conjunto de clases y exportar el resultado para crear un esquema nuevo.) Es posible que no se devuelva el mismo esquema. Invertir el proceso no garantiza tampoco conservar la fidelidad. (Exporte un tipo para generar su esquema y, a continuación, importe el tipo de nuevo. Es improbable que se devuelva el mismo tipo.)  
  
## <a name="supported-types"></a>Tipos admitidos  
 El modelo del contrato de datos solo admite un subconjunto limitado del esquema de WC3. Cualquier esquema que no se ajusta a este subconjunto producirá una excepción durante el proceso de importación. Por ejemplo, no hay ninguna manera de especificar que un miembro de datos de un contrato de datos deba serializarse como un atributo XML. Así, los esquemas que requieren el uso de atributos XML no se admiten y producirán excepciones durante la importación ya que es imposible generar un contrato de datos con la proyección de XML correcta.  
  
 Por ejemplo, el fragmento del esquema siguiente no se puede importar utilizando los valores de importación predeterminados.  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#9](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  -->  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Si un esquema no se ajusta a las reglas del contrato de datos, utilice un motor de serialización diferente. Por ejemplo, el <xref:System.Xml.Serialization.XmlSerializer> utiliza su propio mecanismo de importación de esquema independiente. Además, hay un modo especial de importación en el que se expande el intervalo de esquema compatible. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]la sección sobre la generación de <xref:System.Xml.Serialization.IXmlSerializable> tipos de [esquema de importación para generar clases de](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter` admite cualquier tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que pueda serializarse con `DataContractSerializer`. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tipos admitidos por el serializador de contratos de datos](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Tenga en cuenta que el esquema generado mediante la `XsdDataContractExporter` son normalmente datos válidos que el `XsdDataContractImporter` puede utilizar (a menos que la <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> se utiliza para personalizar el esquema).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mediante la <xref:System.Runtime.Serialization.XsdDataContractImporter>, consulte [esquema de importación para generar clases de](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mediante la <xref:System.Runtime.Serialization.XsdDataContractExporter>, consulte [Exportar esquemas de las clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 [Importación del esquema para generar clases](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)   
 [Exportar esquemas a partir de clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)