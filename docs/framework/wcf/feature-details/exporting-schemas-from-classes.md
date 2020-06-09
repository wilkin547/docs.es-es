---
title: Exportación de esquemas desde las clases
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, schema import and export
- schemas [WCF], exporting from classes
- schemas [WCF]
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: bb57b962-70c1-45a9-93d5-e721e340a13f
ms.openlocfilehash: d356450af8ce6690e2142f3487e153bcde095324
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595523"
---
# <a name="exporting-schemas-from-classes"></a>Exportación de esquemas desde las clases
Para generar esquemas (XSD) de lenguaje de definición de esquemas XML a partir de las clases utilizadas en el modelo de contrato de datos, utilice la clase <xref:System.Runtime.Serialization.XsdDataContractExporter> . En este tema se describe el proceso para crear los esquemas.  
  
## <a name="the-export-process"></a>Proceso de exportación  
 El proceso de exportación de esquema se inicia con uno o más tipos y genera un <xref:System.Xml.Schema.XmlSchemaSet> que describe la proyección de XML de estos tipos.  
  
 Forma `XmlSchemaSet` parte del modelo de objetos de esquema (SOM) del .NET Framework que representa un conjunto de documentos de esquema XSD. Para crear documentos XSD a partir de `XmlSchemaSet`, utilice la colección de esquemas de la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> de la clase `XmlSchemaSet` . A continuación, serialice cada objeto <xref:System.Xml.Schema.XmlSchema> mediante <xref:System.Xml.Serialization.XmlSerializer>.  
  
#### <a name="to-export-schemas"></a>Exportar esquemas  
  
1. Creación de una instancia de <xref:System.Runtime.Serialization.XsdDataContractExporter>.  
  
2. Opcional. Pase <xref:System.Xml.Schema.XmlSchemaSet> en el constructor. En este caso, el esquema generado durante la exportación del esquema se agrega a esta instancia <xref:System.Xml.Schema.XmlSchemaSet> en lugar de iniciarse con un <xref:System.Xml.Schema.XmlSchemaSet>en blanco.  
  
3. Opcional. Llame a uno de los métodos <xref:System.Runtime.Serialization.XsdDataContractExporter.CanExport%2A> . El método determina si se puede exportar el tipo especificado. El método tiene las mismas sobrecargas que el método `Export` en el siguiente paso.  
  
4. Llame a uno de los métodos <xref:System.Runtime.Serialization.XsdDataContractExporter.Export%2A> . Hay tres sobrecargas que toman <xref:System.Type>, <xref:System.Collections.Generic.List%601> de los objetos `Type` , o <xref:System.Collections.Generic.List%601> de los objetos <xref:System.Reflection.Assembly> . En el último caso, se exportan todos los tipos de todos los ensamblados determinados.  
  
     Varias llamadas al método `Export` produce como resultado varios elementos que se agregan al mismo `XmlSchemaSet`. Un tipo no se genera en `XmlSchemaSet` si ya existe en este. Por consiguiente, llamar varias veces `Export` en el mismo `XsdDataContractExporter` es preferible a crear varias instancias de la clase `XsdDataContractExporter` . Esto evita que se generen tipos de esquema duplicados.  
  
    > [!NOTE]
    > Si se produce un error durante la exportación, `XmlSchemaSet` estará en un estado imprevisible.  
  
5. Obtenga acceso a <xref:System.Xml.Schema.XmlSchemaSet> a través de la propiedad <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas%2A> .  
  
## <a name="export-options"></a>Exportar opciones.  
 Puede establecer la propiedad <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A> de <xref:System.Runtime.Serialization.XsdDataContractExporter> a una instancia de <xref:System.Runtime.Serialization.ExportOptions> para administrar varios aspectos del proceso de exportación. En concreto, puede establecer las opciones siguientes:  
  
- <xref:System.Runtime.Serialization.ExportOptions.KnownTypes%2A>. Esta colección de `Type` representa los tipos conocidos para los tipos que se van a exportar. (Para obtener más información, vea [tipos conocidos de contratos de datos](data-contract-known-types.md)). Estos tipos conocidos se exportan en cada `Export` llamada además de los tipos pasados al `Export` método.  
  
- <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A>. <xref:System.Runtime.Serialization.IDataContractSurrogate> se puede proporcionar a través de esta propiedad que personalizará el proceso de exportación. Para obtener más información, vea [suplentes del contrato de datos](../extending/data-contract-surrogates.md). De forma predeterminada, no se utiliza ningún suplente.  
  
## <a name="helper-methods"></a>métodos del asistente  
 Además de su función primaria de exportar el esquema, `XsdDataContractExporter` proporciona varios métodos del asistente útiles que proporcionan información sobre los tipos. Se incluyen los siguientes:  
  
- Método<xref:System.Runtime.Serialization.XsdDataContractExporter.GetRootElementName%2A> . Este método toma `Type` y devuelve <xref:System.Xml.XmlQualifiedName> que representa el nombre del elemento raíz y espacio de nombres que se utilizarían si este tipo se serializara como objeto raíz.  
  
- Método<xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaTypeName%2A> . Este método toma `Type` y devuelve <xref:System.Xml.XmlQualifiedName> que representa el nombre del tipo de esquema XSD que se utilizaría si este tipo se exportara al esquema. Para los tipos <xref:System.Xml.Serialization.IXmlSerializable> representados como tipos anónimos en el esquema, este método devuelve `null`.  
  
- Método<xref:System.Runtime.Serialization.XsdDataContractExporter.GetSchemaType%2A> . Este método solo funciona con tipos <xref:System.Xml.Serialization.IXmlSerializable> representados como tipos anónimos en el esquema y devuelve `null` para el resto de tipos. Para los tipos anónimos, este método devuelve <xref:System.Xml.Schema.XmlSchemaType> que representa un `Type`determinado.  
  
 Las opciones de exportación afectan a todos estos métodos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- [Importación y exportación de esquemas](schema-import-and-export.md)
- [Importación del esquema para generar clases](importing-schema-to-generate-classes.md)
