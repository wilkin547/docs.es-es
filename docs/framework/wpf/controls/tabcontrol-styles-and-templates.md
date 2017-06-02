---
title: "Estilos y plantillas de TabControl | Microsoft Docs"
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
  - "ControlTemplate [WPF], TabControl"
  - "partes [WPF], TabControl"
  - "estados [WPF], TabControl"
  - "estilos [WPF], TabControl"
  - "TabControl [WPF], estilos y plantillas"
  - "plantillas [WPF], TabControl"
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Estilos y plantillas de TabControl
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.TabControl>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de TabControl  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.TabControl>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_SelectedContentHost|<xref:System.Windows.Controls.ContentPresenter>|Objeto que muestra el contenido del control <xref:System.Windows.Controls.TabItem> actualmente seleccionado.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.TabControl>, la plantilla puede contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.  \(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.TabControl>; el <xref:System.Windows.Controls.ScrollViewer> permite el desplazamiento dentro del control\).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe asignar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## Estados de TabControl  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.TabControl>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de TabItem  
 El control <xref:System.Windows.Controls.TabItem> no tiene ningún elemento con nombre.  
  
## Estados de TabItem  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.TabItem>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|Seleccionado|SelectionStates|El control está activado.|  
|No seleccionado|SelectionStates|El control no está seleccionado.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de TabControl  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para los controles <xref:System.Windows.Controls.TabControl> y <xref:System.Windows.Controls.TabItem>.  
  
 [!code-xml[ControlTemplateExamples#TabControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
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