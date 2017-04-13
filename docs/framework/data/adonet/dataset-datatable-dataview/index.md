---
title: "DataSets, DataTables y DataViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSets, DataTables y DataViews
El <xref:System.Data.DataSet> de ADO.NET es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene.  Un <xref:System.Data.DataSet> representa un conjunto completo de datos, incluyendo las tablas que contienen, ordenan y restringen los datos, así como las relaciones entre las tablas.  
  
 Hay varias maneras de trabajar con un <xref:System.Data.DataSet>, que se pueden aplicar de forma independiente o conjuntamente.  Puede realizar lo siguiente:  
  
-   Crear mediante programación una <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> y una <xref:System.Data.Constraint> en un <xref:System.Data.DataSet> y rellenar las tablas con datos.  
  
-   Llenar el <xref:System.Data.DataSet> con tablas de datos de un origen de datos relacional existente mediante `DataAdapter`.  
  
-   Cargar y hacer persistente el contenido de <xref:System.Data.DataSet> mediante XML.  Para obtener más información, consulta [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
 También se puede transportar un <xref:System.Data.DataSet> fuertemente tipado mediante un servicio Web XML.  El diseño del <xref:System.Data.DataSet> lo convierte en idóneo para el transporte de datos mediante servicios Web XML.  Para obtener información general sobre servicios Web XML, vea [XML Web Services Overview](http://msdn.microsoft.com/es-es/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d).  Para ver un ejemplo de cómo utilizar un <xref:System.Data.DataSet> de un servicio Web XML, vea [Consumir DataSet a partir de un servicio Web XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md).  
  
## En esta sección  
 [Crear un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset.md)  
 Describe la sintaxis para crear una instancia de <xref:System.Data.DataSet>.  
  
 [Agregar DataTable a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-a-datatable-to-a-dataset.md)  
 Describe cómo crear tablas y columnas y cómo agregarlas a un <xref:System.Data.DataSet>.  
  
 [Agregar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 Describe cómo se crean las relaciones entre tablas en un <xref:System.Data.DataSet>.  
  
 [Navegar por DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md)  
 Describe cómo se utilizan las relaciones entre tablas en un <xref:System.Data.DataSet> para devolver la filas secundarias o primarias de una relación primaria\-secundaria.  
  
 [Combinar contenido de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/merging-dataset-contents.md)  
 Describe cómo se combina el contenido de una matriz de <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> con otro <xref:System.Data.DataSet>.  
  
 [Copiar contenido de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md)  
 Describe cómo se crea una copia de un <xref:System.Data.DataSet> que puede contener datos de esquema y datos especificados.  
  
 [Controlar eventos de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataset-events.md)  
 Describe los eventos de un <xref:System.Data.DataSet> y cómo utilizarlos.  
  
 [DataSets con establecimiento de tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 Explica lo que es un <xref:System.Data.DataSet> con información de tipos y cómo crearlo y utilizarlo.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Describe cómo se crea una <xref:System.Data.DataTable>, cómo se define el esquema y cómo se manipulan los datos.  
  
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 Describe cómo crear y utilizar un objeto <xref:System.Data.DataTableReader>.  
  
 [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 Describe cómo se crean `DataViews` y cómo se trabaja con ellas, así como con eventos <xref:System.Data.DataView>.  
  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo interactúa el <xref:System.Data.DataSet> con XML como origen de datos, incluyendo cómo cargar y hacer persistente el contenido de un <xref:System.Data.DataSet> como datos XML.  
  
 [Consumir DataSet a partir de un servicio Web XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/consuming-a-dataset-from-an-xml-web-service.md)  
 Describe cómo crear un servicio Web XML que utilice un <xref:System.Data.DataSet> para transportar los datos.  
  
## Secciones relacionadas  
 [Novedades en ADO.NET](../../../../../docs/framework/data/adonet/whats-new.md)  
 Presenta características nuevas en ADO.NET.  
  
 [Información general sobre ADO.NET](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 Proporciona una introducción al diseño y a los componentes de ADO.NET.  
  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 Describe cómo se carga un **DataSet** con datos desde un origen de datos.  
  
 [Actualizar orígenes de datos con DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 Describe cómo se resuelven los cambios relacionados con los datos de un **DataSet** en el origen de datos.  
  
 [Agregar restricciones existentes a DataSet](../../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 Describe cómo se rellena un **DataSet** con información de clave principal de un origen de datos.  
  
## Vea también  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)