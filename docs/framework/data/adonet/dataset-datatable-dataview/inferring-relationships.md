---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493001"
---
# <a name="inferring-relationships"></a>Inferir relaciones
Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas. Una nueva columna con el nombre de **ParentTableName_Id** se agregará a la tabla creada para el elemento primario y la tabla creada para el elemento secundario. El **ColumnMapping** propiedad de esta columna de identidad se establecerá en **MappingType.Hidden**. La columna será una clave principal de incremento automático para la tabla primaria y se usará para la **DataRelation** entre las dos tablas. El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**. Un <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** también se creará con la nueva columna en el elemento primario y secundario de las tablas.  
  
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
  
 El **Element1** tabla tendrá dos columnas: **Element1_Id** y **ChildElement2**. El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**. El **ColumnMapping** propiedad de la **ChildElement2** columna se establecerá en **MappingType.Element**. El **Element1_Id** columna se establecerá como la clave principal de la **Element1** tabla.  
  
 El **ChildElement1** tabla tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**. El **ColumnMapping** propiedad para el **attr1** y **attr2** columnas se establecerá en **MappingType.Attribute**. El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.  
  
 Un **DataRelation** y **ForeignKeyConstraint** , se creará con el **Element1_Id** columnas de ambas tablas.  
  
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
  
 **Anidado:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Columna:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** en cascada  
  
 **AcceptRejectRule:** ninguno  
  
## <a name="see-also"></a>Vea también  
 [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Carga de información del esquema de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Anidado de objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
