---
title: "Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos"
  - "DataGrid (control) [Windows Forms], comparado con el control DataGridView"
  - "DataGridView (control) [Windows Forms], comparado con el control DataGrid"
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> es un nuevo control que reemplaza el control <xref:System.Windows.Forms.DataGrid>.  El control <xref:System.Windows.Forms.DataGridView> proporciona muchas características básicas y avanzadas que faltan en el control <xref:System.Windows.Forms.DataGrid>.  Además, la arquitectura del control <xref:System.Windows.Forms.DataGridView> hace mucho más fácil la ampliación y personalización que el control <xref:System.Windows.Forms.DataGrid>.  
  
 En la tabla siguiente se describen algunas características principales disponibles en el control <xref:System.Windows.Forms.DataGridView> que faltan en el control <xref:System.Windows.Forms.DataGrid>.  
  
|Característica del control DataGridView|Descripción|  
|---------------------------------------------|-----------------|  
|Varios tipos de columna|El control <xref:System.Windows.Forms.DataGridView> proporciona más tipos de columna integrados que el control <xref:System.Windows.Forms.DataGrid>.  Estos tipos de columna satisfacen las necesidades de los escenario más habituales, pero también son más fáciles de ampliar y reemplazar que los tipos de columna del control <xref:System.Windows.Forms.DataGrid>.  Para obtener más información, vea [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de mostrar los datos|El control <xref:System.Windows.Forms.DataGrid> se limita a mostrar los datos desde un origen de datos externo.  El control <xref:System.Windows.Forms.DataGridView>, sin embargo, puede mostrar datos independientes almacenados en el control, datos de un origen de datos enlazado, o datos sin enlazar y enlazados juntos.  También puede implementar el modo virtual en el control <xref:System.Windows.Forms.DataGridView> para proporcionar una administración de datos personalizada.  Para obtener más información, vea [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de personalizar la presentación de datos|El control <xref:System.Windows.Forms.DataGridView> proporciona muchas propiedades y eventos que le permiten especificar cómo dar formato y mostrar los datos.  Por ejemplo, puede cambiar la apariencia de las celdas, filas y columnas dependiendo de los datos que contiene, o puede reemplazar los datos de un tipo de datos con datos equivalentes de otro tipo.  Para obtener más información, vea [Formato de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Varias opciones para cambiar la apariencia y comportamiento de celdas, filas, columnas y encabezados|El control <xref:System.Windows.Forms.DataGridView> le permite trabajar de varias maneras con componentes de cuadrícula individuales.  Por ejemplo, puede inmovilizar filas y columnas para evitar que se desplacen; ocultar filas, columnas y encabezados; cambiar la forma de ajustar los tamaños de fila, columna y encabezado; cambiar la forma de los usuarios de realizar selecciones; y proporcionar menús contextuales e información sobre herramientas para celdas, filas y columnas individuales.|  
  
 El control <xref:System.Windows.Forms.DataGrid> se conserva para compatibilidad con versiones anteriores y para necesidades especiales.  En casi todas las ocasiones, debería utilizar el control <xref:System.Windows.Forms.DataGridView>.  La única característica disponible en el control <xref:System.Windows.Forms.DataGrid> que no dispone el control <xref:System.Windows.Forms.DataGridView> es la presentación jerárquica de información desde dos tablas relacionadas en un único control.  Debe utilizar dos controles <xref:System.Windows.Forms.DataGridView> para mostrar información desde dos tablas que tienen una relación de principal\-detalle.  
  
## Actualizar el control DataGridView  
 Si cuenta con aplicaciones que utilizan el control <xref:System.Windows.Forms.DataGrid> en un sencillo escenario de enlace a datos sin personalizaciones, simplemente reemplace el control antiguo con el nuevo.  Ambos controles utiliza la arquitectura enlazada a datos de los formularios Windows Forms, por lo que el control <xref:System.Windows.Forms.DataGridView> mostrará los datos enlazados sin necesitar ninguna configuración adicional.  Sin embargo, también querrá sacar el máximo partido a las mejoras de los enlaces a datos enlazando sus datos a un componente<xref:System.Windows.Forms.BindingSource>, que puede enlazar a continuación al control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información, vea [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Como el control <xref:System.Windows.Forms.DataGridView> muestra una arquitectura totalmente nueva, no hay ninguna ruta de conversión sencilla que le permite utilizar personalizaciones de <xref:System.Windows.Forms.DataGrid> con el control <xref:System.Windows.Forms.DataGridView>.  Sin embargo, muchas personalizaciones de <xref:System.Windows.Forms.DataGrid> son innecesarias con el control <xref:System.Windows.Forms.DataGridView> debido a las características integradas disponibles en el nuevo control.  Si ha creado tipos de columna personalizadas para el control <xref:System.Windows.Forms.DataGrid> que desea utilizar con el control <xref:System.Windows.Forms.DataGridView>, tendrá que implementarlos de nuevo mediante la nueva arquitectura.  Para obtener más información, vea [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Windows.Forms.BindingSource>   
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Formato de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)   
 [Modos de ordenación de columnas del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Modos de selección en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)   
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)