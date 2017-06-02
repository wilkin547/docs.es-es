---
title: "Resumen de tecnolog&#237;as para el control DataGridView (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, acerca de las cuadrículas de datos"
  - "DataGridView (control) [Windows Forms], acerca del control DataGridView"
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Resumen de tecnolog&#237;as para el control DataGridView (formularios Windows Forms)
En este tema, se resume la información sobre el control `DataGridView` y las clases que admiten su uso.  
  
 Probablemente realizará a menudo la tarea de mostrar datos en formato de tabla.  Se ha diseñado el control `DataGridView` como una solución completa para presentar los datos en una cuadrícula.  
  
## Keywords  
 DataGridView, BindingSource, tabla, celda, enlace de datos, modo virtual  
  
## Espacios de nombres  
 <xref:System.Windows.Forms?displayProperty=fullName>  
  
 <xref:System.Data?displayProperty=fullName>  
  
## Tecnologías relacionadas  
 `BindingSource`  
  
## Background  
 Los diseñadores de la interfaz del usuario \(IU\) suelen encontrar necesario mostrar datos en formato de tabla a los usuarios.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona varias maneras de mostrar los datos en una tabla o cuadrícula.  El control `DataGridView` representa la evolución última de esta tecnología para las aplicaciones de Windows Forms.  
  
 El control `DataGridView` puede mostrar filas de datos de un almacén de datos.  Se admiten muchos tipos de almacenes de datos.  El almacén de datos puede contener datos simples, sin tipo, como una matriz unidimensional, o puede contener datos con tipo, como <xref:System.Data.DataSet>.  Para obtener más información, vea [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla.  Puede utilizar el control para mostrar vistas de pequeños a grandes conjuntos de datos de sólo lectura o modificables.  
  
 Puede ampliar el control `DataGridView` de varias maneras para integrar el comportamiento personalizado en las aplicaciones.  Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y crear sus propios tipos de celdas.  Puede personalizar con facilidad la apariencia del control `DataGridView` eligiendo entre varias propiedades.  Se pueden utilizar muchos tipos de almacenes de datos como origen de datos o el control `DataGridView` puede operar sin tener ningún origen de datos enlazado.  
  
## Implementar las clases DataGridView  
 Hay varias maneras de aprovechar las ventajas de las características de extensibilidad del control `DataGridView`.  Puede personalizar muchos aspectos del control mediante eventos y propiedades, pero algunas personalizaciones requieren que se creen nuevas clases derivadas de clases `DataGridView` existentes.  
  
 Las clases base más utilizadas son `DataGridViewCell` y `DataGridViewColumn`.  Puede derivar su propia clase de célula de `DataGridViewCell` o de cualquiera de sus clases secundarias.  Aunque puede agregar cualquier tipo de celda a cualquier columna, normalmente también derivará una clase de columna acompañante de `DataGridViewColumn` que hospeda celdas del tipo de celda personalizado predeterminado.  
  
 Puede implementar la interfaz `IDataGridViewEditingCell` en la clase de celda derivada para crear un tipo de celda que tiene funciones de edición pero que no hospeda controles en el modo de edición.  Para crear controles que puede hospedar en celdas en el modo de edición, puede implementar la interfaz `IDataGridViewEditingControl` en una clase derivada de <xref:System.Windows.Forms.Control>.  
  
 Para obtener más información, vea [Cómo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) y [Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## Breve introducción a las clases DataGridView  
 <xref:System.Windows.Forms>  
  
|Área de tecnología|Clases\/interfaces\/elementos de configuración|  
|------------------------|----------------------------------------------------|  
|Enlace de datos|<xref:System.Windows.Forms.BindingSource>|  
|Presentación de los datos|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|Extensibilidad de <xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Forms.DataGridViewCell> y clases derivadas<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> y clases derivadas<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## Lo nuevo  
 Se ha diseñado el control <xref:System.Windows.Forms.DataGridView> como una solución completa para mostrar datos en formato de tabla con formularios Windows Forms.  Debería considerar utilizar el control <xref:System.Windows.Forms.DataGridView> antes de otras soluciones, como <xref:System.Windows.Forms.DataGrid>, cuando crea una nueva aplicación.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 El control <xref:System.Windows.Forms.DataGridView> puede funcionar en estrecha conjunción con el componente <xref:System.Windows.Forms.BindingSource>.  Este componente está diseñado para ser el origen de datos primario de un formulario.  Puede administrar la interacción entre un control <xref:System.Windows.Forms.DataGridView> y su origen de datos, sin tener en cuenta el tipo de origen de datos.  
  
## Vea también  
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)