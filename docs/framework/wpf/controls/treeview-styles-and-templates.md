---
title: "Estilos y plantillas de TreeView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], TreeView"
  - "partes [WPF], TreeView"
  - "estados [WPF], TreeView"
  - "estilos [WPF], TreeView"
  - "plantillas [WPF], TreeView"
  - "TreeView [WPF], estilos y plantillas"
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Estilos y plantillas de TreeView
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.TreeView>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de TreeView  
 El control <xref:System.Windows.Controls.TreeView> no tiene ningún elemento con nombre.  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.TreeView>, la plantilla puede contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.  \(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.TreeView>; el <xref:System.Windows.Controls.ScrollViewer> permite el desplazamiento dentro del control\).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe asignar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## Estados de TreeView  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.TreeView>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de TreeViewItem  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.TreeViewItem>.  
  
|Parte|Tipo|Descripción|  
|-----------|----------|-----------------|  
|PART\_Header|<xref:System.Windows.FrameworkElement>|Elemento visual que incluye el contenido del encabezado del control <xref:System.Windows.Controls.TreeView>.|  
  
## Estados de TreeViewItem  
 En la siguiente tabla se muestran los estados visuales del control <xref:System.Windows.Controls.TreeViewItem>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre el control <xref:System.Windows.Controls.TreeViewItem>.|  
|Disabled|CommonStates|El control <xref:System.Windows.Controls.TreeViewItem> está deshabilitado.|  
|Focused|FocusStates|El control <xref:System.Windows.Controls.TreeViewItem> tiene el foco.|  
|Unfocused|FocusStates|El control <xref:System.Windows.Controls.TreeViewItem> no tiene el foco.|  
|Expandido|ExpansionStates|El control <xref:System.Windows.Controls.TreeViewItem> está expandido.|  
|Collapsed|ExpansionStates|El control <xref:System.Windows.Controls.TreeViewItem> está contraído.|  
|HasItems|HasItemsStates|El control <xref:System.Windows.Controls.TreeViewItem> tiene elementos.|  
|NoItems|HasItemsStates|El control <xref:System.Windows.Controls.TreeViewItem> no tiene elementos.|  
|Seleccionado|SelectionStates|El control <xref:System.Windows.Controls.TreeViewItem> está seleccionado.|  
|SelectedInactive|SelectionStates|El control <xref:System.Windows.Controls.TreeViewItem> está seleccionado, pero no activo.|  
|No seleccionado|SelectionStates|El control <xref:System.Windows.Controls.TreeViewItem> no está seleccionado.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de TreeView  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.TreeView> y sus tipos asociados.  
  
 [!code-xml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 El ejemplo anterior utiliza uno o más de los siguientes recursos.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para obtener el ejemplo completo, vea          [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)