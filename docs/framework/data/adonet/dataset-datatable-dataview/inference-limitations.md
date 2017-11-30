---
title: Limitaciones de inferencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98ea3d5fa4427b391ef06b3fc6ace9a05dfb819a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inference-limitations"></a>Limitaciones de inferencia
El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento. Por ejemplo, considere los siguientes documentos XML.  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 En el caso de "Document1," el proceso de inferencia produce una **conjunto de datos** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento de repetición.  
  
 **Conjunto de datos:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Sin embargo, para "Document2", el proceso de inferencia produce una **conjunto de datos** con el nombre "NewDataSet" y una tabla denominada "DocumentElement". "Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.  
  
 **Conjunto de datos:** NewDataSet  
  
 **Tabla:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.  
  
 Para evitar las discrepancias que pueden producirse al generar el esquema de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML (XSD) o datos XML reducidos (XDR) al cargar un **conjunto de datos** desde XML. Para obtener más información acerca de cómo especificar explícitamente un **conjunto de datos** esquema con el esquema XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Vea también  
 [Deducir la estructura relacional de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Cargar un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
