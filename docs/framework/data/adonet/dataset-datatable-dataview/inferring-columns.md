---
description: Más información acerca de cómo deducir columnas
title: Inferir columnas
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 528d4ea20260b5f1fbf30536eafcaec8c5f9215a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652255"
---
# <a name="inferring-columns"></a>Inferir columnas

Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas. ADO.NET 2,0 presentó un nuevo motor de inferencia de esquemas que deduce un tipo de datos fuertemente tipado para cada elemento **simpleType** . En versiones anteriores, el tipo de datos de un elemento **simpleType** deducido siempre era **xsd: String**.  
  
## <a name="migration-and-backward-compatibility"></a>Migración y compatibilidad con versiones anteriores  

 El método **ReadXml** toma un argumento de tipo **InferSchema**. Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores. En la tabla siguiente se muestran los valores disponibles para la enumeración **InferSchema** .  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 Infiere un tipo de datos fuertemente tipado. Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.  
  
## <a name="attributes"></a>Atributos  

 Como se define en [inferencia de tablas](inferring-tables.md), un elemento con atributos se deduce como una tabla. Los atributos de dicho elemento se deducirán como columnas de la tabla. La propiedad **ColumnMapping** de las columnas se establecerá en **MappingType. Attribute** para asegurarse de que los nombres de columna se escribirán como atributos si el esquema se vuelve a escribir en XML. Los valores de los atributos se almacenan en una fila de la tabla. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **attr1** y **attr2**. La propiedad **ColumnMapping** de ambas columnas se establecerá en **MappingType. Attribute**.  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="elements-without-attributes-or-child-elements"></a>Elementos sin atributos o elementos secundarios  

 Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna. La propiedad **ColumnMapping** de la columna se establecerá en **MappingType. Element**. El texto de los elementos secundarios se almacena en una fila de la tabla. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas, **ChildElement1** y **ChildElement2**. La propiedad **ColumnMapping** de ambas columnas se establecerá en **MappingType. Element**.  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## <a name="see-also"></a>Vea también

- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
