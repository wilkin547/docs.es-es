---
title: Inferir texto de elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203527"
---
# <a name="inferring-element-text"></a>Inferir texto de elemento
Si un elemento contiene texto y no tiene ningún elemento secundario que se infiera como tabla (como elementos con atributos o elementos repetidos), se agregará una nueva columna con el nombre **TableName_Text** a la tabla que se infiere para el elemento. El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna. La propiedad **ColumnMapping** de la nueva columna se establecerá en **MappingType. SimpleContent**.  
  
 Por ejemplo, tomemos el siguiente código XML.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1_Text**. La propiedad **ColumnMapping** de la columna **attr1** se establecerá en **MappingType. Attribute**. La propiedad **ColumnMapping** de la columna **Element1_Text** se establecerá en **MappingType. SimpleContent**.  
  
 **Authors1** DocumentElement  
  
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
  
 El proceso de inferencia producirá una tabla denominada **Element1** con una columna denominada **ChildElement1**. El texto del elemento **ChildElement1** se incluirá en una fila de la tabla. El otro texto se pasará por alto. La propiedad **ColumnMapping** de la columna **ChildElement1** se establecerá en **MappingType. Element**.  
  
 **Authors1** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>Vea también

- [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Carga de un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Carga de información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
