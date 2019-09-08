---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 4c9c13453e4a830fcda337e8163649ba6491a995
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785363"
---
# <a name="inferring-relationships"></a>Inferir relaciones
Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas. Se agregará una nueva columna con el nombre **ParentTableName_Id** a la tabla creada para el elemento primario y a la tabla creada para el elemento secundario. La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType. Hidden**. La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas. El tipo de datos de la columna de identidad agregada será **System. Int32**, a diferencia del tipo de datos de todas las demás columnas inferidos, que es **System. String**. También <xref:System.Data.ForeignKeyConstraint> se creará una con la**cascada** de **DeleteRule** = utilizando la nueva columna en las tablas primaria y secundaria.  
  
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
  
 La tabla **Element1** tendrá dos columnas: **Element1_Id** y **ChildElement2**. La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**. La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType. Element**. La columna **Element1_Id** se establecerá como la clave principal de la tabla **Element1** .  
  
 La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**. La propiedad **ColumnMapping** de las columnas **attr1** y **Attr2** se establecerá en **MappingType. Attribute**. La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.  
  
 Se creará una **DataRelation** y **ForeignKeyConstraint** usando las columnas **Element1_Id** de ambas tablas.  
  
 **Authors1** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabla:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Anidada** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Artículo** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## <a name="see-also"></a>Vea también

- [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Carga de un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Carga de información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Anidado de objetos DataRelation](nesting-datarelations.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
