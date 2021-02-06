---
description: Más información acerca de cómo deducir tablas
title: Inferir tablas
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 00a24cbfc44aea4279b0a115214ec26d3eac59ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652164"
---
# <a name="inferring-tables"></a>Inferir tablas

Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas. Las siguientes estructuras XML dan como resultado una tabla para el esquema del **conjunto** de elementos:  
  
- Elementos con atributos  
  
- Elementos con elementos secundarios  
  
- Elementos que se repiten  
  
## <a name="elements-with-attributes"></a>Elementos con atributos  

 Los elementos para los que se han especificado atributos se deducen como tablas. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## <a name="elements-with-child-elements"></a>Elementos con elementos secundarios  

 Los elementos que tienen elementos secundarios se deducen como tablas. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas. Si el elemento de documento no tiene ningún atributo y ningún elemento secundario que se deduzca como columnas, el elemento se deduce como un **conjunto** de elementos. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "DocumentElement".  
  
 **Conjunto** de los: NewDataSet  
  
 **Tabla:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Por otra parte, considere el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce un **DataSet** denominado "DocumentElement" que contiene una tabla denominada "Element1".  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## <a name="repeating-elements"></a>Elementos que se repiten  

 Los elementos que se repiten se deducen como una única tabla. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **Conjunto** de los: DocumentElement  
  
 **Tabla:** Elemento1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>Vea también

- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
