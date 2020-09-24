---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177571"
---
# <a name="inferring-relationships"></a>Inferir relaciones

Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas. Se agregará una nueva columna con el nombre **ParentTableName_Id** a la tabla creada para el elemento primario y a la tabla creada para el elemento secundario. La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType. Hidden**. La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas. El tipo de datos de la columna de identidad agregada será **System. Int32**, a diferencia del tipo de datos de todas las demás columnas inferidos, que es **System. String**. <xref:System.Data.ForeignKeyConstraint>También se **DeleteRule**  =  creará una con la**cascada** de DeleteRule utilizando la nueva columna en las tablas primaria y secundaria.  
  
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
  
 La tabla **Element1** tendrá dos columnas: **Element1_Id** y **ChildElement2**. La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**. La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType. Element**. La columna de **Element1_Id** se establecerá como la clave principal de la tabla **Element1** .  
  
 La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**. La propiedad **ColumnMapping** de las columnas **attr1** y **Attr2** se establecerá en **MappingType. Attribute**. La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.  
  
 Se creará una **DataRelation** y **ForeignKeyConstraint** utilizando el **Element1_Id** columnas de ambas tablas.  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabla:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Elemento1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Anidado:** Reales  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Columna:** Element1_Id  
  
 **ParentTable:** Elemento1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** Ninguna  
  
## <a name="see-also"></a>Consulte también

- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Anidar objetos DataRelation](nesting-datarelations.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
