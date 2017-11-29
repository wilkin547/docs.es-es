---
title: "Resumen de tecnologías para el control DataGridView (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f172d28e5f03e1177db6ad1bd9e98f4c68267765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Resumen de tecnologías para el control DataGridView (formularios Windows Forms)
En este tema se resume la información sobre el control `DataGridView` y las clases que admiten su uso.  
  
 Mostrar datos en formato tabular es una tarea que es probable que realice frecuentemente. El `DataGridView` control está diseñado para ser una solución completa para presentar datos en una cuadrícula.  
  
## <a name="keywords"></a>Palabras clave  
 DataGridView, BindingSource, tabla, celda, enlace de datos, modo virtual  
  
## <a name="namespaces"></a>Espacios de nombres  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologías relacionadas  
 `BindingSource`  
  
## <a name="background"></a>Fondo  
 Diseñadores de interfaz de usuario suelen encontrar necesario mostrar datos tabulares a los usuarios. El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona varias maneras de mostrar datos en una tabla o cuadrícula. El `DataGridView` control representa la evolución más reciente de esta tecnología para aplicaciones de Windows Forms.  
  
 El `DataGridView` control puede mostrar filas de datos de un almacén de datos. Se admiten muchos tipos de almacenes de datos. El almacén de datos puede contener datos simples, sin tipo, como una matriz unidimensional, o puede contener datos con tipo, como un <xref:System.Data.DataSet>. Para obtener más información, consulte [Cómo: enlazar datos al DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla. Puede utilizar el control para mostrar vistas de solo lectura o editables de pequeños a grandes conjuntos de datos.  
  
 Puede ampliar el `DataGridView` control de varias maneras para construir el comportamiento personalizado en sus aplicaciones. Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y puede crear sus propios tipos de celdas. Puede personalizar fácilmente la apariencia del control `DataGridView` eligiendo entre varias propiedades. Muchos tipos de almacenes de datos pueden utilizarse como origen de datos, o la `DataGridView` control puede funcionar sin un origen de datos enlazado a él.  
  
## <a name="implementing-datagridview-classes"></a>Implementación de clases de DataGridView  
 Hay varias maneras para que pueda aprovechar las ventajas de la `DataGridView` características de extensibilidad del control. Puede personalizar muchos aspectos del control a través de eventos y propiedades, pero algunas personalizaciones requieren que se creen nuevas clases derivadas de existente `DataGridView` clases.  
  
 Las clases base más utilizadas son `DataGridViewCell` y `DataGridViewColumn`. Puede derivar su propia clase de celda de `DataGridViewCell` o cualquiera de sus clases secundarias. Aunque puede agregar cualquier tipo de celda a cualquier columna, normalmente también derivará una clase de columna complementaria de `DataGridViewColumn` que hospeda celdas del tipo de celda personalizado de forma predeterminada.  
  
 Puede implementar la `IDataGridViewEditingCell` interfaz en la clase de celda derivada para crear un tipo de celda que tiene funciones de edición, pero no hospede un control en modo de edición. Para crear un control que se puede hospedar en una celda en modo de edición, puede implementar la `IDataGridViewEditingControl` interfaz en una clase derivada de <xref:System.Windows.Forms.Control>.  
  
 Para obtener más información, consulte [Cómo: personalizar celdas y columnas en el DataGridView Control de formularios Windows Forms por extender su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) y [Cómo: hospedar controles en celdas DataGridView de formularios Windows](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Un vistazo a las clases DataGridView  
 <xref:System.Windows.Forms>  
  
|Área de tecnología|Clases/interfaces/elementos de configuración|  
|---------------------|-------------------------------------------------|  
|Enlace de datos|<xref:System.Windows.Forms.BindingSource>|  
|Presentación de los datos|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell>y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewRow>y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView>Extensibilidad|<xref:System.Windows.Forms.DataGridViewCell>y las clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>y las clases derivadas<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novedades  
 El <xref:System.Windows.Forms.DataGridView> control está diseñado para ser una solución completa para mostrar datos tabulares con formularios Windows Forms. Puede utilizar el <xref:System.Windows.Forms.DataGridView> de control antes de otras soluciones, como <xref:System.Windows.Forms.DataGrid>, cuando está creando una nueva aplicación. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 El <xref:System.Windows.Forms.DataGridView> control puede funcionar en estrecha conjunción con el <xref:System.Windows.Forms.BindingSource> componente. Este componente está diseñado para ser el origen de datos principal de un formulario. Puede administrar la interacción entre un <xref:System.Windows.Forms.DataGridView> control y su origen de datos, independientemente de los datos de tipo de origen.  
  
## <a name="see-also"></a>Vea también  
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
