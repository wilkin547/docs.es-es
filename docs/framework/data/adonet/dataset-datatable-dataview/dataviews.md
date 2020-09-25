---
title: Objetos DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: c5692fcfd1863642bcdf87cbd495d793bce0cbe4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203714"
---
# <a name="dataviews"></a>Objetos DataView

Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Mediante una **DataView**, puede exponer los datos de una tabla con distintos criterios de ordenación, y puede filtrar los datos por estado de fila o en función de una expresión de filtro.

 Una **DataView** proporciona una vista dinámica de los datos en la **DataTable**subyacente: el contenido, el orden y la pertenencia reflejan los cambios a medida que se producen. Este comportamiento difiere del método **Select** de la **DataTable**, que devuelve una <xref:System.Data.DataRow> matriz de una tabla basada en un filtro o criterio de ordenación concreto: este contenido refleja los cambios en la tabla subyacente, pero su pertenencia y ordenación permanecen estáticas. Las capacidades dinámicas de **DataView** hacen que sea ideal para aplicaciones de enlace de datos.

 Una **DataView** proporciona una vista dinámica de un único conjunto de datos, como una vista de base de datos, a la que puede aplicar distintos criterios de ordenación y filtrado. A diferencia de una vista de base de datos, sin embargo, una **DataView** no se puede tratar como una tabla y no puede proporcionar una vista de las tablas combinadas. Tampoco puede excluir columnas que existan en la tabla de origen ni anexar columnas que no existan en la tabla de origen, como columnas de cálculo.

 Puede utilizar un <xref:System.Data.DataView.DataViewManager%2A> **objeto**para administrar la configuración de vista para todas las tablas de un conjunto de información. El **DataViewManager** proporciona una manera cómoda de administrar la configuración de vista predeterminada para cada tabla. Al enlazar un control a más de una tabla de un conjunto de información, el enlace a un **objeto** **DataViewManager** es la opción ideal.

## <a name="in-this-section"></a>En esta sección

 [Crear una DataView](creating-a-dataview.md) Describe cómo crear una **DataView** para una **DataTable**.

 [Ordenar y filtrar datos](sorting-and-filtering-data.md) Describe cómo establecer las propiedades de una **DataView** para devolver subconjuntos de filas de datos que cumplen los criterios de filtro específicos o para devolver los datos en un criterio de ordenación determinado.

 [DataRows y DataRowView](datarows-and-datarowviews.md) Describe cómo obtener acceso a los datos expuestos por **DataView**.

 [Buscar filas](finding-rows.md) Describe cómo buscar una fila determinada en una **DataView**.

 [Objetos ChildView y relaciones](childviews-and-relations.md) Describe cómo crear vistas de datos a partir de una relación de elementos primarios y secundarios mediante una **DataView**.

 [Modificar las vistas de vista](modifying-dataviews.md) Describe cómo modificar los datos de la **DataTable** subyacente a través de **DataView**, incluida la habilitación o deshabilitación de actualizaciones.

 [Controlar eventos de DataView](handling-dataview-events.md) Describe cómo utilizar el evento **ListChanged** para recibir notificaciones cuando se actualiza el contenido o el orden de una **DataView** .

 [Administrar los visores](managing-dataviews.md) Describe cómo utilizar un objeto **DataViewManager** para administrar la configuración de **DataView** para cada tabla de un **conjunto**de valores.

## <a name="related-sections"></a>Secciones relacionadas

 [Aplicaciones Web ASP.net](/previous-versions/655cec97(v=vs.100)) Proporciona información general y procedimientos detallados paso a paso para crear aplicaciones de ASP.NET, formularios Web Forms y servicios Web.

 [Aplicaciones Windows](/previous-versions/ms184421(v=vs.100)) Proporciona información detallada sobre cómo trabajar con Windows Forms y aplicaciones de consola.

 [Conjuntos de valores, DataTables y DataTables](index.md) Describe el objeto **DataSet** y cómo se puede utilizar para administrar los datos de la aplicación.

 [DataTables](datatables.md) Describe el objeto **DataTable** y cómo se puede utilizar para administrar los datos de la aplicación por sí solo o como parte de un **conjunto**de datos.

 [ADO.net](../index.md) Describe la arquitectura y los componentes de ADO.NET y cómo usar ADO.NET para tener acceso a los orígenes de datos existentes y administrar los datos de la aplicación.

## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](../ado-net-overview.md)
