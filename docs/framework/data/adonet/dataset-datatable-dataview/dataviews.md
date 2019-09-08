---
title: Objetos DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 8a06accb11631f2dce6b0d39587d7274223c0e68
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786348"
---
# <a name="dataviews"></a>Objetos DataView
Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Mediante una **DataView**, puede exponer los datos de una tabla con distintos criterios de ordenación, y puede filtrar los datos por estado de fila o en función de una expresión de filtro.  
  
 Una **DataView** proporciona una vista dinámica de los datos en la **DataTable**subyacente: el contenido, el orden y la pertenencia reflejan los cambios a medida que se producen. Este comportamiento difiere del método **Select** de la **DataTable**, que devuelve una <xref:System.Data.DataRow> matriz de una tabla basada en un filtro o un criterio de ordenación determinados: este contenido refleja los cambios en la tabla subyacente, pero su pertenencia y el orden sigue siendo estático. Las capacidades dinámicas de **DataView** hacen que sea ideal para aplicaciones de enlace de datos.  
  
 Una **DataView** proporciona una vista dinámica de un único conjunto de datos, como una vista de base de datos, a la que puede aplicar distintos criterios de ordenación y filtrado. A diferencia de una vista de base de datos, sin embargo, una **DataView** no se puede tratar como una tabla y no puede proporcionar una vista de las tablas combinadas. Tampoco puede excluir columnas que existen en la tabla de origen ni puede anexar columnas, como columnas de cálculo, que no existen en la tabla de origen.  
  
 Puede utilizar un <xref:System.Data.DataView.DataViewManager%2A> objeto para administrar la configuración de vista para todas las tablas de un **conjunto**de información. El **DataViewManager** proporciona una manera cómoda de administrar la configuración de vista predeterminada para cada tabla. Al enlazar un control a más de una tabla de un conjunto de información, el enlace a un **objeto** **DataViewManager** es la opción ideal.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataView](creating-a-dataview.md)  
 Describe cómo crear una **DataView** para una **DataTable**.  
  
 [Ordenación y filtrado de datos](sorting-and-filtering-data.md)  
 Describe cómo establecer las propiedades de una **DataView** para devolver subconjuntos de filas de datos que cumplen los criterios de filtro específicos o para devolver los datos en un criterio de ordenación determinado.  
  
 [DataRow y DataRowView](datarows-and-datarowviews.md)  
 Describe cómo obtener acceso a los datos expuestos por **DataView**.  
  
 [Búsqueda de filas](finding-rows.md)  
 Describe cómo buscar una fila determinada en una **DataView**.  
  
 [ChildView y Relation](childviews-and-relations.md)  
 Describe cómo crear vistas de datos a partir de una relación de elementos primarios y secundarios mediante una **DataView**.  
  
 [Modificación de objetos DataView](modifying-dataviews.md)  
 Describe cómo modificar los datos de la **DataTable** subyacente a través de **DataView**, incluida la habilitación o deshabilitación de actualizaciones.  
  
 [Control de eventos de DataView](handling-dataview-events.md)  
 Describe cómo utilizar el evento **ListChanged** para recibir notificaciones cuando se actualiza el contenido o el orden de una **DataView** .  
  
 [Administración de objetos DataView](managing-dataviews.md)  
 Describe cómo utilizar un objeto **DataViewManager** para administrar la configuración de **DataView** para cada tabla de un **conjunto**de valores.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Aplicaciones web de ASP.NET](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))  
 Proporciona información general y procedimientos detallados paso a paso sobre la creación de aplicaciones ASP.NET, Web Forms y servicios Web.  
  
 [Aplicaciones Windows](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))  
 Proporciona información detallada sobre el uso de Windows Forms y aplicaciones de consola.  
  
 [Objetos DataSet, DataTable y DataView](index.md)  
 Describe el objeto **DataSet** y cómo se puede utilizar para administrar los datos de la aplicación.  
  
 [Objetos DataTable](datatables.md)  
 Describe el objeto **DataTable** y cómo se puede utilizar para administrar los datos de la aplicación por sí solo o como parte de un **conjunto**de datos.  
  
 [ADO.NET](../index.md)  
 Describe la arquitectura y los componentes de ADO.NET así como su uso para obtener acceso a orígenes de datos existentes y administrar los datos de las aplicaciones.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../ado-net-overview.md)
