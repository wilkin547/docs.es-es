---
title: Importación y exportación de esquemas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
ms.openlocfilehash: 9f13f9d95c40b964c5eb416c590a5d603d714bac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991021"
---
# <a name="schema-import-and-export"></a>Importación y exportación de esquemas
Windows Communication Foundation (WCF) incluye un nuevo motor de serialización, el <xref:System.Runtime.Serialization.DataContractSerializer>. `DataContractSerializer` traduce entre los objetos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y XML (en ambas direcciones). Además del propio serializador, WCF incluye mecanismos de exportación de esquema y de importación del esquema asociado. *Esquema* es una descripción formal, exacta y legible de la forma del XML que el serializador genera o que pueda tener acceso el deserializador. WCF usa el lenguaje de definición de esquema XML de World Wide Web Consortium (W3C) (XSD) como la representación del esquema, que es muy interoperable con numerosas plataformas de terceros.  
  
 El componente de importación de esquema, <xref:System.Runtime.Serialization.XsdDataContractImporter>, toma un documento de esquema XSD y genera las clases [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (normalmente las clases de contrato de datos) de manera que los formularios serializados se corresponden con el esquema dado.  
  
 Por ejemplo, el fragmento de esquema siguiente:  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 genera el tipo siguiente (simplificado ligeramente para una mejor interpretación).  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 Tenga en cuenta que el tipo generado sigue los procedimientos recomendados del contrato de datos en varios (se encuentra en [prácticas recomendadas: Control de versiones de contratos de datos](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):  
  
- El tipo implementa la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>. Para obtener más información, vea [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío).  
  
- Los miembros de datos se implementan como propiedades públicas que se ajustan a los campos privados.  
  
- La clase es una clase parcial y se pueden realizar adiciones sin modificar el código generado.  
  
 <xref:System.Runtime.Serialization.XsdDataContractExporter> le permite hacer lo contrario: tomar los tipos que son serializables con `DataContractSerializer` y generar un documento de esquema XSD.  
  
## <a name="fidelity-is-not-guaranteed"></a>La fidelidad no está garantizada  
 No se garantiza que el esquema o los tipos realicen un viaje de ida y vuelta (round trip) con fidelidad total. (Un *ida y vuelta* significa importar un esquema para crear un conjunto de clases y exportar el resultado para crear un esquema nuevo.) Es posible que no se devuelva el mismo esquema. Invertir el proceso no garantiza tampoco conservar la fidelidad. (Exporte un tipo para generar su esquema y, a continuación, importe el tipo de nuevo. Es improbable que se devuelva el mismo tipo.)  
  
## <a name="supported-types"></a>Tipos admitidos  
 El modelo del contrato de datos solo admite un subconjunto limitado del esquema de WC3. Cualquier esquema que no se ajusta a este subconjunto producirá una excepción durante el proceso de importación. Por ejemplo, no hay ninguna manera de especificar que un miembro de datos de un contrato de datos deba serializarse como un atributo XML. Así, los esquemas que requieren el uso de atributos XML no se admiten y producirán excepciones durante la importación ya que es imposible generar un contrato de datos con la proyección de XML correcta.  
  
 Por ejemplo, el fragmento del esquema siguiente no se puede importar utilizando los valores de importación predeterminados.  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 Para obtener más información, consulte [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Si un esquema no se ajusta a las reglas del contrato de datos, utilice un motor de serialización diferente. Por ejemplo, <xref:System.Xml.Serialization.XmlSerializer> utiliza su propio mecanismo de importación de esquema independiente. Además, hay un modo especial de importación en el que se expande el intervalo de esquema compatible. Para obtener más información, vea la sección acerca de cómo generar <xref:System.Xml.Serialization.IXmlSerializable> tipos [esquema de importación para generar clases](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 `XsdDataContractExporter` admite cualquier tipo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que pueda serializarse con `DataContractSerializer`. Para obtener más información, consulte [tipos admitidos por el serializador de contratos de datos](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md). Tenga en cuenta que el esquema generado mediante `XsdDataContractExporter` son normalmente datos válidos que `XsdDataContractImporter` puede utilizar (a menos que se use <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> para personalizar el esquema).  
  
 Para obtener más información sobre el uso de la <xref:System.Runtime.Serialization.XsdDataContractImporter>, consulte [esquema de importación para generar clases](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).  
  
 Para obtener más información sobre el uso de la <xref:System.Runtime.Serialization.XsdDataContractExporter>, consulte [Exportar esquemas desde las clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Importación del esquema para generar clases](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)
- [Exportación de esquemas desde las clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
