---
title: "Información general del control DataGridView (Formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d9cc6568813af866acaf20696b870bedc3099be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-overview-windows-forms"></a>Información general del control DataGridView (Formularios Windows Forms)
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Con el <xref:System.Windows.Forms.DataGridView> control, puede mostrar y editar datos tabulares desde muchos tipos diferentes de orígenes de datos.  
  
 Enlazar datos a la <xref:System.Windows.Forms.DataGridView> control es sencillo e intuitivo y en muchos casos resulta tan sencillo como configuración de la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad. Al enlazar a un origen de datos que contiene varias listas o tablas, establecer el <xref:System.Windows.Forms.DataGridView.DataMember%2A> propiedad a una cadena que especifica la lista o tabla que se va a enlazar.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de formularios Windows Forms estándar, por lo que se enlazará a instancias de las clases descritas en la lista siguiente:  
  
-   Cualquier clase que implemente la <xref:System.Collections.IList> interfaz, incluidas las matrices unidimensionales.  
  
-   Cualquier clase que implemente la <xref:System.ComponentModel.IListSource> interfaz, como el <xref:System.Data.DataTable> y <xref:System.Data.DataSet> clases.  
  
-   Cualquier clase que implemente la <xref:System.ComponentModel.IBindingList> interfaz, como la <xref:System.ComponentModel.BindingList%601> clase.  
  
-   Cualquier clase que implemente la <xref:System.ComponentModel.IBindingListView> interfaz, como la <xref:System.Windows.Forms.BindingSource> clase.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el enlace de datos a las propiedades públicas de los objetos devueltos por estas interfaces o a la colección de propiedades devuelta por un <xref:System.ComponentModel.ICustomTypeDescriptor> de la interfaz, si se implementa en los objetos devueltos.  
  
 Normalmente, se enlazará a un <xref:System.Windows.Forms.BindingSource> componente y se enlaza la <xref:System.Windows.Forms.BindingSource> componente a otro origen de datos o rellenar con objetos de negocios. El <xref:System.Windows.Forms.BindingSource> componente es el origen de datos preferido porque puede enlazar a una amplia variedad de orígenes de datos y puede resolver muchos problemas de enlace de datos automáticamente. Para obtener más información, consulte [BindingSource (componente)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 El <xref:System.Windows.Forms.DataGridView> control también puede usarse en *sin enlazar* modo con ningún almacén de datos subyacente. Para obtener un ejemplo de código que usa un independiente <xref:System.Windows.Forms.DataGridView> control, vea [Tutorial: crear un DataGridView Control de Windows Forms independientes](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 El <xref:System.Windows.Forms.DataGridView> control es altamente configurable y extensible y proporciona muchas propiedades, métodos y eventos para personalizar su apariencia y comportamiento. Si desea que la aplicación de formularios Windows Forms para mostrar datos tabulares, considere el uso de la <xref:System.Windows.Forms.DataGridView> control antes que otras (por ejemplo, <xref:System.Windows.Forms.DataGrid>). Si va a mostrar una cuadrícula pequeña de valores de solo lectura, o si va a habilitar un usuario editar una tabla con millones de registros, la <xref:System.Windows.Forms.DataGridView> control le proporcionará una solución eficaz de memoria y fácilmente programable.  
  
## <a name="in-this-section"></a>En esta sección  
 [Resumen de tecnologías para el control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Resume <xref:System.Windows.Forms.DataGridView> controlar conceptos y el uso de clases relacionadas.  
  
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Describe la arquitectura de la <xref:System.Windows.Forms.DataGridView> (control), que explica su estructura de jerarquía y herencia de tipo.  
  
 [Escenarios del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Describe los escenarios más comunes en los que <xref:System.Windows.Forms.DataGridView> se usan los controles.  
  
 [Directorio de código del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Proporciona vínculos a ejemplos de código de la documentación para los distintos <xref:System.Windows.Forms.DataGridView> tareas. Estos ejemplos se dividen por categorías de tipo de tarea.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna en los formularios Windows Forms <xref:System.Windows.Forms.DataGridView> control utilizado para mostrar información y permitir a los usuarios modificar o agregar información.  
  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.  
  
 [Personalizar el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView (control)](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Funcionalidad predeterminada en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
