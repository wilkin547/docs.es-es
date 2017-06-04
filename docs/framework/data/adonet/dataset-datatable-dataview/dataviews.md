---
title: "DataViews | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataViews
Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos.  Mediante una **DataView** puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro.  
  
 Una **DataView** proporciona una vista de datos dinámica en la **DataTable**subyacente: el contenido, el orden y la pertenencia reflejan los cambios en cuanto se producen.  Este comportamiento difiere del método **Select** de la **DataTable**, que devuelve una matriz de <xref:System.Data.DataRow> de una tabla basada en un filtro o un criterio de ordenación determinados: este contenido refleja cambios en la tabla subyacente, pero la pertenencia y la ordenación siguen siendo estáticas.  Las capacidades dinámicas de la **DataView** hacen que resulte ideal para las aplicaciones de enlace a datos.  
  
 Una **DataView** proporciona una vista dinámica de un único conjunto de datos, similar a la vista de una base de datos, a la que puede aplicar distintos criterios de ordenación y filtrado.  Sin embargo, al contrario que una vista de base de datos, una **DataView** no puede tratarse como una tabla y no puede proporcionar una vista de tablas combinadas.  Tampoco puede excluir columnas que existen en la tabla de origen ni puede anexar columnas, como columnas de cálculo, que no existen en la tabla de origen.  
  
 Puede utilizar un <xref:System.Data.DataView.DataViewManager%2A> para administrar la configuración de vista para todas las tablas de un **DataSet**.  El **DataViewManager** proporciona una forma cómoda de administrar la configuración de vista predeterminada para cada tabla.  Al enlazar un control a más de una tabla de un **DataSet**, el enlace a un **DataViewManager** es la elección ideal.  
  
## En esta sección  
 [Crear DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Describe cómo se crea una **DataView** para una **DataTable**.  
  
 [Ordenar y filtrar datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Describe cómo establecer las propiedades de una **DataView** para devolver subconjuntos de filas de datos que reúnan determinados criterios de filtro o para devolver datos con un criterio de ordenación concreto.  
  
 [DataRows y DataRowViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Describe cómo tener acceso a los datos expuestos por la **DataView**.  
  
 [Buscar filas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Describe cómo buscar una fila determinada en una **DataView**.  
  
 [ChildViews y relaciones](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Describe cómo crear vistas de datos a partir de una relación primaria\-secundaria con una **DataView**.  
  
 [Modificar objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Describe cómo modificar los datos de la **DataTable** subyacente mediante la **DataView**, así como la forma de habilitar y deshabilitar las actualizaciones.  
  
 [Tratamiento de eventos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Describe cómo utilizar el evento **ListChanged** para recibir una notificación cuando se actualice el contenido o el orden de una **DataView**.  
  
 [Administrar DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Describe cómo utilizar un **DataViewManager** para administrar la configuración de **DataView** para todas las tablas de un **DataSet**.  
  
## Secciones relacionadas  
 [ASP.NET Web Applications](http://msdn.microsoft.com/es-es/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Proporciona información general y procedimientos detallados paso a paso sobre la creación de aplicaciones ASP.NET, Web Forms y servicios Web.  
  
 [Windows Applications](http://msdn.microsoft.com/es-es/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Proporciona información detallada sobre el uso de Windows Forms y aplicaciones de consola.  
  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe el objeto **DataSet** y cómo puede utilizarlo para administrar datos de aplicación.  
  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Describe el objeto **DataTable** y cómo puede utilizarlo para administrar datos de aplicación por sí solos o como parte de un **DataSet**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET así como su uso para obtener acceso a orígenes de datos existentes y administrar los datos de las aplicaciones.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)