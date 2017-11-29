---
title: Inferir relaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 41c73ac31105cdae0a23c2367211747dee8d44f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-relationships"></a>Inferir relaciones
Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas. Una nueva columna con el nombre de **ParentTableName_Id** se agregará a la tabla creada para el elemento primario y de la tabla creada para el elemento secundario. El **ColumnMapping** propiedad de esta columna de identidad se establecerá en **MappingType.Hidden**. La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas. El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**. A <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** también se creará con la nueva columna de tablas el elemento primario y el secundario.  
  
 Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.  
  
 El **Element1** tabla tiene dos columnas: **Element1_Id** y **ChildElement2**. El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**. El **ColumnMapping** propiedad de la **ChildElement2** columna se establecerá en **MappingType.Element**. El **Element1_Id** columna se establecerá como la clave principal de la **Element1** tabla.  
  
 El **ChildElement1** tabla tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**. El **ColumnMapping** propiedad para la **attr1** y **attr2** columnas se establecerá en **MappingType.Attribute**. El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.  
  
 A **DataRelation** y **ForeignKeyConstraint** se creará usando la **Element1_Id** columnas de ambas tablas.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabla:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Anidadas:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Columna:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** en cascada  
  
 **AcceptRejectRule:** ninguno  
  
## <a name="see-also"></a>Vea también  
 [Deducir la estructura relacional de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Cargar un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
