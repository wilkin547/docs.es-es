---
title: "Limitaciones de la inferencia | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Limitaciones de la inferencia
El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento.  Por ejemplo, considere los siguientes documentos XML.  
  
 Document1:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 En el caso de "Document1", el proceso de inferencia produce un **DataSet** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento que se repite.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Sin embargo, en el caso de "Document2", el proceso de inferencia produce un **DataSet** denominado "NewDataSet" y una tabla denominada "DocumentElement". "Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.  
  
 **DataSet:** NewDataSet  
  
 **Tabla:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.  
  
 Para evitar las discrepancias que pueden producirse al generar el esquema a partir de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML \(XSD\) o el reducido de datos XML \(XDR\) al cargar un **DataSet** desde XML.  Para obtener más información sobre cómo especificar de forma explícita un esquema de **DataSet** con esquema XML, vea [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)