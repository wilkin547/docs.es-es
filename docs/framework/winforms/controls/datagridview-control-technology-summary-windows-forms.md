---
title: Resumen de tecnologías para el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 18eebd067df9768e14cc81258184551d00dd1402
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742478"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Resumen de tecnologías para el control DataGridView (formularios Windows Forms)
En este tema se resume la información sobre el control `DataGridView` y las clases que admiten su uso.  
  
 La visualización de datos en formato tabular es una tarea que es probable que realice con frecuencia. El control de `DataGridView` está diseñado para ser una solución completa para presentar los datos en una cuadrícula.  
  
## <a name="keywords"></a>Palabras clave  
 DataGridView, BindingSource, tabla, celda, enlace de datos, modo virtual  
  
## <a name="namespaces"></a>Espacios de nombres  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologías relacionadas  
 `BindingSource`  
  
## <a name="background"></a>Información previa  
 Los diseñadores de la interfaz de usuario (UI) suelen encontrar que es necesario mostrar los datos tabulares a los usuarios. El .NET Framework proporciona varias maneras de mostrar los datos en una tabla o cuadrícula. El control de `DataGridView` representa la evolución más reciente de esta tecnología para las aplicaciones de Windows Forms.  
  
 El control `DataGridView` puede mostrar filas de datos de un almacén de datos. Se admiten muchos tipos de almacenes de datos. El almacén de datos puede contener datos simples sin tipo, como una matriz unidimensional, o puede contener datos con tipo, como un <xref:System.Data.DataSet>. Para obtener más información, vea [Cómo: enlazar datos al control DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla. Puede usar el control para mostrar vistas de solo lectura o editables de conjuntos de datos pequeños o muy grandes.  
  
 Puede extender el control `DataGridView` de varias maneras para compilar el comportamiento personalizado en sus aplicaciones. Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y puede crear sus propios tipos de celdas. Puede personalizar fácilmente la apariencia del control `DataGridView` eligiendo entre varias propiedades. Muchos tipos de almacenes de datos se pueden usar como origen de datos o el control `DataGridView` puede funcionar sin un origen de datos enlazado.  
  
## <a name="implementing-datagridview-classes"></a>Implementar clases DataGridView  
 Hay varias maneras de aprovechar las características de extensibilidad del control `DataGridView`. Puede personalizar muchos aspectos del control a través de eventos y propiedades, pero algunas personalizaciones requieren la creación de nuevas clases derivadas de las clases de `DataGridView` existentes.  
  
 Las clases base más utilizadas normalmente son `DataGridViewCell` y `DataGridViewColumn`. Puede derivar su propia clase de celda de `DataGridViewCell` o cualquiera de sus clases secundarias. Aunque puede agregar cualquier tipo de celda a cualquier columna, normalmente también derivará una clase de columna complementaria de `DataGridViewColumn` que hospede celdas del tipo de celda personalizado de forma predeterminada.  
  
 Puede implementar la interfaz de `IDataGridViewEditingCell` en la clase de celda derivada para crear un tipo de celda que tenga funcionalidad de edición pero que no hospede un control en modo de edición. Para crear un control que pueda hospedar en una celda en modo de edición, puede implementar la interfaz `IDataGridViewEditingControl` en una clase derivada de <xref:System.Windows.Forms.Control>.  
  
 Para obtener más información, vea [Cómo: personalizar celdas y columnas en el Control Windows Forms DataGridView extendiendo su comportamiento y aspecto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) y [Cómo: hospedar controles en Windows Forms celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Clases DataGridView de un vistazo  
 <xref:System.Windows.Forms>  
  
|Área de tecnología|Clases/interfaces/elementos de configuración|  
|---------------------|-------------------------------------------------|  
|Enlace de datos|<xref:System.Windows.Forms.BindingSource>|  
|Presentación de datos|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|extensibilidad de <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridViewCell> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y clases derivadas<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>What's New  
 El control de <xref:System.Windows.Forms.DataGridView> está diseñado para ser una solución completa para Mostrar datos tabulares con Windows Forms. Debe considerar la posibilidad de usar el control de <xref:System.Windows.Forms.DataGridView> antes que otras soluciones, como <xref:System.Windows.Forms.DataGrid>, cuando se crea una nueva aplicación. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 El control <xref:System.Windows.Forms.DataGridView> puede funcionar en estrecha colaboración con el componente <xref:System.Windows.Forms.BindingSource>. Este componente está diseñado para ser el origen de datos principal de un formulario. Puede administrar la interacción entre un control de <xref:System.Windows.Forms.DataGridView> y su origen de datos, independientemente del tipo de origen de datos.  
  
## <a name="see-also"></a>Consulte también

- [Información general del control DataGridView](datagridview-control-overview-windows-forms.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
