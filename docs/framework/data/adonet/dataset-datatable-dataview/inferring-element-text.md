---
title: Inferir texto de elemento
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 239c70ca0e7f8894b988f17d248b2e5b3b98bf6a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-element-text"></a>Inferir texto de elemento
Si el elemento contiene texto y no tiene elementos secundarios que se deducen como tablas (como elementos con atributos) o elementos repetidos, una nueva columna con el nombre **TableName_Text** se agregará a la tabla que se deduzca para el elemento. El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna. El **ColumnMapping** propiedad de la nueva columna se establecerá en **MappingType.SimpleContent**.  
  
 Por ejemplo, tomemos el siguiente código XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1_Text**. El **ColumnMapping** propiedad de la **attr1** columna se establecerá en **MappingType.Attribute**. El **ColumnMapping** propiedad de la **Element1_Text** columna se establecerá en **MappingType.SimpleContent**.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Si un elemento contiene texto, pero también tiene elementos secundarios que contienen texto, no se agregará una columna a la tabla para almacenar el texto contenido en el elemento. El texto contenido en el elemento se pasará por alto, mientras que el texto de los elementos secundarios se incluirá en una fila de la tabla. Por ejemplo, tomemos el siguiente código XML.  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con una columna denominada **ChildElement1**. El texto de la **ChildElement1** elemento se incluirá en una fila de la tabla. El otro texto se pasará por alto. El **ColumnMapping** propiedad de la **ChildElement1** columna se establecerá en **MappingType.Element**.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Vea también  
 [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Carga de información del esquema de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
