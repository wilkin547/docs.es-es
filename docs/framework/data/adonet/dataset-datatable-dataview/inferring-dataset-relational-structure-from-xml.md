---
title: Inferir una estructura relacional de un conjunto de datos a partir de XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5a846bc321aab19cb1d04ba55ca4cca4b7188bcd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="inferring-dataset-relational-structure-from-xml"></a>Inferir una estructura relacional de un conjunto de datos a partir de XML
La estructura relacional, o esquema, de un <xref:System.Data.DataSet> está compuesta por tablas, columnas, restricciones y relaciones. Al cargar un <xref:System.Data.DataSet> desde XML es posible predefinir el esquema, o bien crearlo, de forma explícita o por inferencia, a partir del código XML que se carga. Para obtener más información acerca de cómo cargar el esquema y el contenido de un <xref:System.Data.DataSet> de XML, vea [cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) y [cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
 Si el esquema de un <xref:System.Data.DataSet> se crea desde XML, el método preferido consiste en especificar explícitamente el esquema mediante el esquema XML definición lenguaje (XSD) (como se describe en [derivar estructura relacional de DataSet de esquemas XML (XSD) ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)) o los datos XML reducen (XDR). Si no hay ningún esquema XML o XDR disponible en XML, el esquema del <xref:System.Data.DataSet> se puede deducir de la estructura de los elementos y atributos XML.  
  
 En esta sección se describen las reglas para deducir el esquema de un <xref:System.Data.DataSet>; para ello se muestran los elementos y atributos XML y su estructura, así como el esquema deducido del <xref:System.Data.DataSet> resultante.  
  
 No todos los atributos presentes en un documento XML deben incluirse en el proceso de deducción. Los atributos calificados por el espacio de nombres pueden incluir metadatos importantes para el documento XML, pero no para el esquema del <xref:System.Data.DataSet>. Mediante <xref:System.Data.DataSet.InferXmlSchema%2A> es posible especificar determinados espacios de nombres que desea pasar por alto durante el proceso de inferencia. Para obtener más información, consulte [cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Resumen del proceso de inferencia del esquema de conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/summary-of-the-dataset-schema-inference-process.md)  
 Proporciona un resumen general de las reglas para deducir el esquema de un <xref:System.Data.DataSet> a partir de XML.  
  
 [Inferir tablas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)  
 Describe los elementos XML que se deducen como tablas en un <xref:System.Data.DataSet>.  
  
 [Inferir columnas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-columns.md)  
 Describe los elementos y atributos XML que se deducen como columnas de tabla.  
  
 [Deducir relaciones](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-relationships.md)  
 Describe los objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> creados para tablas deducidas y anidadas.  
  
 [Deducir texto de elemento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-element-text.md)  
 Describe las columnas que se crean para texto en los elementos XML y explica cuándo se pasa por alto el texto de los elementos XML.  
  
 [Limitaciones de inferencia](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inference-limitations.md)  
 Describe las limitaciones de la inferencia del esquema.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo interactúa el objeto <xref:System.Data.DataSet> con los datos XML.  
  
 [Derivar la estructura relacional de un conjunto de datos de esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional o un esquema de un <xref:System.Data.DataSet> que se crea a partir del esquema del lenguaje de definición de esquemas XML (XSD).  
  
 [Información general sobre ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Describe la arquitectura y los componentes de ADO.NET, así como su uso para obtener acceso a orígenes de datos existentes y para administrar los datos de aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
