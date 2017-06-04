---
title: "Estilos y plantillas de ComboBox | Microsoft Docs"
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
  - "ComboBox [WPF], estilos y plantillas"
  - "ControlTemplate [WPF], ComboBox"
  - "partes [WPF], ComboBox"
  - "estados [WPF], ComboBox"
  - "estilos [WPF], ComboBox"
  - "plantillas [WPF], ComboBox"
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Estilos y plantillas de ComboBox
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.ComboBox>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de ComboBox  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.ComboBox>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_EditableTextBox|<xref:System.Windows.Controls.TextBox>|Contiene el texto de <xref:System.Windows.Controls.ComboBox>.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Elemento desplegable que contiene los elementos del cuadro combinado.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ComboBox>, la plantilla puede contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.  \(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ComboBox>; el <xref:System.Windows.Controls.ScrollViewer> permite el desplazamiento dentro del control\).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe asignar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## Estados de ComboBox  
 En la siguiente tabla se muestran los estados del control <xref:System.Windows.Controls.ComboBox>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se encuentra encima del control <xref:System.Windows.Controls.ComboBox>.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|FocusedDropDown|FocusStates|El elemento desplegable de <xref:System.Windows.Controls.ComboBox> tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
|Modificable|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `true`.|  
|Uneditable|EditStates|La propiedad <xref:System.Windows.Controls.ComboBox.IsEditable%2A> es `false`.|  
  
## Elementos de ComboBoxItem  
 El control <xref:System.Windows.Controls.ComboBoxItem> no tiene ningún elemento con nombre.  
  
## Estados de ComboBoxItem  
 En la siguiente tabla se muestran los estados del control <xref:System.Windows.Controls.ComboBoxItem>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse se encuentra encima del control <xref:System.Windows.Controls.ComboBox>.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|Seleccionado|SelectionStates|El elemento está seleccionado.|  
|No seleccionado|SelectionStates|El elemento no está seleccionado.|  
|SelectedUnfocused|SelectionStates|El elemento está seleccionado pero no tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de ComboBox  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ComboBox> y los tipos asociados.  
  
 [!code-xml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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