---
title: Resumen de tecnologías para el control DataGridView (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: ca8268137f2a154c782388d0f13cdd02504cbb64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909279"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Resumen de tecnologías para el control DataGridView (formularios Windows Forms)
En este tema se resume la información sobre el control `DataGridView` y las clases que admiten su uso.  
  
 Mostrar datos en formato tabular es una tarea que se pueda realizar con frecuencia. El `DataGridView` control está diseñado para ser una solución completa para presentar datos en una cuadrícula.  
  
## <a name="keywords"></a>Palabras clave  
 DataGridView, BindingSource, tabla, celda, enlace de datos, el modo virtual  
  
## <a name="namespaces"></a>Espacios de nombres  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologías relacionadas  
 `BindingSource`  
  
## <a name="background"></a>Fondo  
 Diseñadores de interfaz de usuario con frecuencia que sea necesario mostrar datos tabulares a los usuarios. El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona varias maneras de mostrar datos en una tabla o una cuadrícula. El `DataGridView` control representa la evolución más reciente de esta tecnología para aplicaciones de Windows Forms.  
  
 El `DataGridView` control puede mostrar las filas de datos desde un almacén de datos. Se admiten muchos tipos de almacenes de datos. El almacén de datos puede contener datos simples sin tipo, como una matriz unidimensional, o puede contener datos con tipo, como un <xref:System.Data.DataSet>. Para obtener más información, vea [Cómo: Enlazar datos a la Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla. Puede utilizar el control para mostrar vistas de solo lectura o editables de pequeños a grandes conjuntos de datos.  
  
 Puede ampliar el `DataGridView` control de varias formas para crear un comportamiento personalizado en las aplicaciones. Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y puede crear sus propios tipos de celdas. Puede personalizar fácilmente la apariencia del control `DataGridView` eligiendo entre varias propiedades. Muchos tipos de almacenes de datos pueden usarse como origen de datos, o el `DataGridView` control puede funcionar sin un origen de datos enlazado a él.  
  
## <a name="implementing-datagridview-classes"></a>Implementación de clases de DataGridView  
 Hay varias maneras de aprovechar la `DataGridView` las características de extensibilidad del control. Puede personalizar muchos aspectos del control mediante propiedades y eventos, pero algunas personalizaciones requieren que se creen nuevas clases derivadas a partir de existente `DataGridView` clases.  
  
 Las clases base más utilizadas son `DataGridViewCell` y `DataGridViewColumn`. Puede derivar su propia clase de celda de `DataGridViewCell` o cualquiera de sus clases secundarias. Aunque puede agregar cualquier tipo de celda a cualquier columna, normalmente también derivará una clase de columna complementaria de `DataGridViewColumn` que hospeda las celdas del tipo de celda personalizado de forma predeterminada.  
  
 Puede implementar la `IDataGridViewEditingCell` interfaz en la clase de celda derivada para crear un tipo de celda que tiene funciones de edición, pero no hospede un control en modo de edición. Para crear un control que puede hospedar en una celda en modo de edición, puede implementar la `IDataGridViewEditingControl` interfaz en una clase derivada de <xref:System.Windows.Forms.Control>.  
  
 Para obtener más información, vea [Cómo: Personalizar celdas y columnas en la Windows Forms DataGridView Control ampliando su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) y [Cómo: Alojar controles en formularios de Windows las celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Un vistazo a las clases DataGridView  
 <xref:System.Windows.Forms>  
  
|Área de tecnología|Clases/interfaces/elementos de configuración|  
|---------------------|-------------------------------------------------|  
|Enlace de datos|<xref:System.Windows.Forms.BindingSource>|  
|Presentación de los datos|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Extensibilidad|<xref:System.Windows.Forms.DataGridViewCell> y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y las clases derivadas<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novedades  
 El <xref:System.Windows.Forms.DataGridView> control está diseñado para ser una solución completa para mostrar datos tabulares con Windows Forms. Puede utilizar el <xref:System.Windows.Forms.DataGridView> de control antes de otras soluciones, como <xref:System.Windows.Forms.DataGrid>, al crear una nueva aplicación. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 El <xref:System.Windows.Forms.DataGridView> control puede funcionar en estrecha junto con el <xref:System.Windows.Forms.BindingSource> componente. Este componente está diseñado para ser el origen de datos principal de un formulario. Puede administrar la interacción entre un <xref:System.Windows.Forms.DataGridView> control y su origen de datos, independientemente de los datos de tipo de origen.  
  
## <a name="see-also"></a>Vea también

- [Información general del control DataGridView](datagridview-control-overview-windows-forms.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
- [Proteger la información de conexión](../../data/adonet/protecting-connection-information.md)
