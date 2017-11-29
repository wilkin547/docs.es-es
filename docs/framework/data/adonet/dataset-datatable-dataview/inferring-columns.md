---
title: Inferir columnas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba06bce55db53de1da1c07d2a6451d5664fa23bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-columns"></a>Inferir columnas
Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas. ADO.NET 2.0 incorporó un nuevo motor de inferencia de esquemas que deduce un tipo de datos fuertemente tipados para cada **simpleType** elemento. En versiones anteriores, el tipo de datos de un deducido **simpleType** elemento siempre era **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migración y compatibilidad con versiones anteriores  
 El **ReadXml** método toma un argumento de tipo **InferSchema**. Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores. Los valores disponibles para la **InferSchema** enumeración se muestran en la tabla siguiente.  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Infiere un tipo de datos fuertemente tipado. Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.  
  
## <a name="attributes"></a>Atributos  
 Tal como se define en [deducir tablas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento con atributos se deducirá como una tabla. Los atributos de dicho elemento se deducirán como columnas de la tabla. El **ColumnMapping** propiedad de las columnas se establecerá en **MappingType.Attribute**para asegurarse de que los nombres de columna se escribirán como atributos si el esquema se vuelve a escribir XML. Los valores de los atributos se almacenan en una fila de la tabla. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **attr1** y **attr2**. El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Attribute**.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elementos sin atributos o elementos secundarios  
 Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna. El **ColumnMapping** propiedad de la columna se establecerá en **MappingType.Element**. El texto de los elementos secundarios se almacena en una fila de la tabla. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **ChildElement1** y **ChildElement2**. El **ColumnMapping** propiedad de ambas columnas se establecerá en **MappingType.Element**.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Vea también  
 [Deducir la estructura relacional de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Cargar un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
