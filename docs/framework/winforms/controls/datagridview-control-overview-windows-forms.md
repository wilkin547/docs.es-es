---
title: "Informaci&#243;n general del control DataGridView (Formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGridView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles enlazados, DataGridView (control)"
  - "columnas [Windows Forms], DataGridView (control)"
  - "datos [Windows Forms], navegar"
  - "datos [Windows Forms], volver a ordenar"
  - "enlace de datos, DataGridView (control)"
  - "cuadrículas de datos, acerca de las cuadrículas de datos"
  - "orígenes de datos, enlazar al control DataGridView"
  - "DataGridView (control) [Windows Forms], acerca del control DataGridView"
  - "DataGridView (control) [Windows Forms], enlace de datos"
  - "conjuntos de datos [Windows Forms], enlazar al control DataGridView"
  - "controles de cuadrícula [Windows Forms]"
  - "cuadrículas [Windows Forms]"
  - "tablas [Windows Forms], enlazar al control DataGridView"
  - "tablas [Windows Forms], mostrar en el control DataGridView"
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Informaci&#243;n general del control DataGridView (Formularios Windows Forms)
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Con el control <xref:System.Windows.Forms.DataGridView> puede mostrar y editar los datos en tablas a partir de numerosos tipos diferentes de orígenes de datos.  
  
 El enlace de datos al control <xref:System.Windows.Forms.DataGridView> es sencillo e intuitivo y en muchos casos es tan fácil como establecer la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>.  Cuando realiza el enlace a un origen de datos que contiene varias listas o tablas, establezca la propiedad <xref:System.Windows.Forms.DataGridView.DataMember%2A> en una cadena que especifica la lista o tabla a la que se va a enlazar.  
  
 El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos de formularios Windows Forms estándar, por lo que se enlazará a las instancias de clases descritas en la lista siguiente:  
  
-   Cualquier clase que implementa la interfaz <xref:System.Collections.IList>, incluidas las matrices unidimensionales.  
  
-   Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IListSource>, como las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet>.  
  
-   Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IBindingList>, como la clase <xref:System.ComponentModel.BindingList%601>.  
  
-   Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IBindingListView>, como la clase <xref:System.Windows.Forms.BindingSource>.  
  
 El control <xref:System.Windows.Forms.DataGridView> admite el enlace de datos a las propiedades públicas de los objetos devueltos por estas interfaces o a la colección de propiedades devuelta por la interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>, si se implementa en los objetos devueltos.  
  
 Normalmente, se enlazará a un componente <xref:System.Windows.Forms.BindingSource> y se enlazará el componente <xref:System.Windows.Forms.BindingSource> a otro origen de datos o se rellenará con objetos de negocios.  El componente <xref:System.Windows.Forms.BindingSource> es el origen de datos preferido porque puede enlazarse a una amplia gama de orígenes de datos y puede resolver automáticamente muchos problemas de enlace de datos.  Para obtener más información, vea [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 El control <xref:System.Windows.Forms.DataGridView> también se puede utilizar en modo *sin enlazar*, sin el almacén de datos subyacente.  Para obtener un ejemplo de código que utiliza un control <xref:System.Windows.Forms.DataGridView> independiente, vea [Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 El control <xref:System.Windows.Forms.DataGridView> es muy configurable y extensible y proporciona muchas propiedades, métodos y eventos para personalizar su aspecto y comportamiento.  Si desea que la aplicación de Windows Forms muestre los datos en formato de tabla, considere utilizar el control <xref:System.Windows.Forms.DataGridView> antes que otros \(por ejemplo, <xref:System.Windows.Forms.DataGrid>\).  Si muestra una pequeña cuadrícula de valores de sólo lectura o si habilita al usuario para editar una tabla con millones de registros, el control <xref:System.Windows.Forms.DataGridView> le proporcionará una solución eficaz de memoria y fácilmente programable.  
  
## En esta sección  
 [Resumen de tecnologías para el control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 Resume conceptos del control <xref:System.Windows.Forms.DataGridView> y el uso de clases relacionadas.  
  
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 Describe la arquitectura del control <xref:System.Windows.Forms.DataGridView>, que explica su jerarquía de tipo y la estructura de herencia.  
  
 [Escenarios del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 Describe los escenarios más comunes en los que se utilizan los controles <xref:System.Windows.Forms.DataGridView>.  
  
 [Directorio de código del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 Proporciona vínculos a los ejemplos de código de la documentación para las distintas tareas de <xref:System.Windows.Forms.DataGridView>.  Estos ejemplos se dividen por categorías de tipo de tarea.  
  
## Secciones relacionadas  
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna del control <xref:System.Windows.Forms.DataGridView> de formularios Windows Forms utilizados para mostrar información y permitir a los usuarios modificar o agregar información.  
  
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos ya sea de forma manual o de un origen de datos externo.  
  
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas en los que se describe el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, así como la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo utilizar eficazmente el control para evitar los problemas de rendimiento al trabajar con grandes cantidades de datos.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)   
 [Control predeterminado de teclado y mouse \(ratón\) en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)