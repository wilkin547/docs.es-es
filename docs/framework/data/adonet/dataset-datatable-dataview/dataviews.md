---
title: Objetos DataView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5b79461a6fc3314ca4178e0f9b1cff1c468cc3e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="dataviews"></a>Objetos DataView
Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Con un **DataView**, puede exponer los datos en una tabla con distintos criterios de ordenación y puede filtrar los datos por estado de fila o basándose en una expresión de filtro.  
  
 A **DataView** proporciona una vista dinámica de datos subyacente **DataTable**: el contenido, el orden y la pertenencia reflejan cambios cuando se producen. Este comportamiento difiere de la **seleccione** método de la **DataTable**, que devuelve un <xref:System.Data.DataRow> matriz a partir de una tabla basada en un criterio de filtro o un orden determinado: thiscontent refleja los cambios en el subyacente de la tabla, pero la pertenencia y ordenación siguen siendo estáticas. Las capacidades dinámicas de la **DataView** hacen que resulte ideal para las aplicaciones de enlace de datos.  
  
 A **DataView** proporciona una vista dinámica de un único conjunto de datos, similar a una vista de base de datos, al que puede aplicar distintos de ordenación y criterios de filtrado. A diferencia de una vista de base de datos, sin embargo, un **DataView** no se puede tratar como una tabla y no puede proporcionar una vista de tablas combinadas. Tampoco puede excluir columnas que existen en la tabla de origen ni puede anexar columnas, como columnas de cálculo, que no existen en la tabla de origen.  
  
 Puede usar un <xref:System.Data.DataView.DataViewManager%2A> para administrar la configuración de vista para todas las tablas en un **conjunto de datos**. El **DataViewManager** proporciona una manera cómoda de administrar la configuración de vista predeterminada para cada tabla. Al enlazar un control a más de una tabla de un **conjunto de datos**, el enlace a un **DataViewManager** es la elección ideal.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-dataview.md)  
 Describe cómo crear un **DataView** para un **DataTable**.  
  
 [Ordenación y filtrado de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 Describe cómo establecer las propiedades de un **DataView** para devolver subconjuntos de filas de datos que reúnan determinados criterios, o para devolver datos en un orden determinado.  
  
 [DataRow y DataRowView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datarows-and-datarowviews.md)  
 Describe cómo obtener acceso a los datos expuestos por el **DataView**.  
  
 [Búsqueda de filas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)  
 Describe cómo buscar una fila determinada en una **DataView**.  
  
 [ChildView y Relation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/childviews-and-relations.md)  
 Describe cómo crear vistas de datos de una relación de elementos primarios y secundarios con un **DataView**.  
  
 [Modificación de objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/modifying-dataviews.md)  
 Describe cómo modificar los datos de subyacente **DataTable** a través de la **DataView**, como habilitar o deshabilitar las actualizaciones.  
  
 [Control de eventos de DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-dataview-events.md)  
 Describe cómo utilizar el **ListChanged** eventos para recibir una notificación cuando el contenido o el orden de un **DataView** se está actualizando.  
  
 [Administración de objetos DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/managing-dataviews.md)  
 Describe cómo usar un **DataViewManager** para administrar **DataView** configuración para cada tabla en un **conjunto de datos**.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Aplicaciones Web ASP.NET](http://msdn.microsoft.com/library/a812d7b7-049e-4234-a4c2-6acf690301f6)  
 Proporciona información general y procedimientos detallados paso a paso sobre la creación de aplicaciones ASP.NET, Web Forms y servicios Web.  
  
 [Aplicaciones de Windows](http://msdn.microsoft.com/library/a6bb2180-09b1-4738-b9fd-7fb05fc92f23)  
 Proporciona información detallada sobre el uso de Windows Forms y aplicaciones de consola.  
  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Describe la **conjunto de datos** objeto y cómo puede utilizarlo para administrar datos de aplicación.  
  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 Describe la **DataTable** objeto y cómo puede utilizarlo para administrar datos de aplicación por sí solo o como parte de un **conjunto de datos**.  
  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Describe la arquitectura y los componentes de ADO.NET así como su uso para obtener acceso a orígenes de datos existentes y administrar los datos de las aplicaciones.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
