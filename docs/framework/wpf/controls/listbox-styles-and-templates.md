---
title: "Estilos y plantillas de ListBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], ListBox"
  - "ListBox [WPF], estilos y plantillas"
  - "partes [WPF], ListBox"
  - "estados [WPF], ListBox"
  - "estilos [WPF], ListBox"
  - "plantillas [WPF], ListBox"
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Estilos y plantillas de ListBox
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.ListBox>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de ListBox  
 El control <xref:System.Windows.Controls.ListBox> no tiene ningún elemento con nombre.  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ListBox>, la plantilla puede contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.  \(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ListBox>; el <xref:System.Windows.Controls.ScrollViewer> permite el desplazamiento dentro del control\).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe asignar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## Estados de ListBox  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.ListBox>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Valid|ValidationStates|El control es válido.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido ni tiene el foco.|  
  
## Elementos de ListBoxItem  
 El control <xref:System.Windows.Controls.ListBoxItem> no tiene ningún elemento con nombre.  
  
## Estados de ListBoxItem  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.ListBox>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Disabled|CommonStates|El elemento está deshabilitado.|  
|Focused|FocusStates|El elemento tiene foco.|  
|Unfocused|FocusStates|El elemento no tiene el foco.|  
|No seleccionado|SelectionStates|El elemento está seleccionado.|  
|Seleccionado|SelectionStates|El elemento no está seleccionado.|  
|SelectedUnfocused|SelectionStates|El elemento está seleccionado pero no tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de ListBox  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para los controles <xref:System.Windows.Controls.ListBox> y <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-xml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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