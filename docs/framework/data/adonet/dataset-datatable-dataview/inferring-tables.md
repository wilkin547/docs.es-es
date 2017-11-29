---
title: Inferir tablas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ae6f7827b7206544ff7547cc04f44b7cda34bef8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-tables"></a>Inferir tablas
Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas. Las siguientes estructuras XML como resultado una tabla para la **conjunto de datos** esquema:  
  
-   Elementos con atributos  
  
-   Elementos con elementos secundarios  
  
-   Elementos que se repiten  
  
## <a name="elements-with-attributes"></a>Elementos con atributos  
 Los elementos para los que se han especificado atributos se deducen como tablas. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
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
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas. Si el elemento de documento tiene ningún atributo y ningún elemento secundario que se deducen como columnas, el elemento se deduce como una **conjunto de datos**. Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "DocumentElement".  
  
 **Conjunto de datos:** NewDataSet  
  
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
  
 El proceso de inferencia produce una **conjunto de datos** denominado "DocumentElement" que contiene una tabla denominada "Element1".  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
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
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## <a name="see-also"></a>Vea también  
 [Deducir la estructura relacional de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Cargar un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
