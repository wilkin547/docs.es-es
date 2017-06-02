---
title: "Estilos y plantillas de DatePicker | Microsoft Docs"
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
  - "ControlTemplate [WPF], DatePicker"
  - "DatePicker [WPF], estilos y plantillas"
  - "partes [WPF], DatePicker"
  - "estados [WPF], DatePicker"
  - "estilos [WPF], DatePicker"
  - "plantillas [WPF], DatePicker"
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Estilos y plantillas de DatePicker
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.DatePicker>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de DatePicker  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.DatePicker>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_Root|<xref:System.Windows.Controls.Grid>|Raíz del control.|  
|PART\_Button|<xref:System.Windows.Controls.Button>|Botón que abre y cierra el control <xref:System.Windows.Controls.Calendar>.|  
|PART\_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|Cuadro de texto que permite especificar una fecha.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|El elemento emergente del control <xref:System.Windows.Controls.DatePicker>.|  
  
## Estados de DatePicker  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.DatePicker>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control <xref:System.Windows.Controls.DatePicker> está deshabilitado.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Elementos de DatePickerTextBox  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_Watermark|<xref:System.Windows.Controls.ContentControl>|Elemento que contiene el texto inicial de <xref:System.Windows.Controls.DatePicker>.|  
|PART\_ContentElement|<xref:System.Windows.FrameworkElement>|Elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.  El texto del control <xref:System.Windows.Controls.TextBox> se muestra en este elemento.|  
  
## Estados de DatePickerTextBox  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está deshabilitado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre el control <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|ReadOnly|CommonStates|El usuario no puede cambiar el texto de <xref:System.Windows.Controls.Primitives.DatePickerTextBox>.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|Watermarked|WatermarkStates|El control muestra el texto inicial.  <xref:System.Windows.Controls.Primitives.DatePickerTextBox> está en dicho estado cuando el usuario no ha escrito texto o seleccionado una fecha.|  
|Unwatermarked|WatermarkStates|El usuario ha escrito texto en <xref:System.Windows.Controls.Primitives.DatePickerTextBox> o ha seleccionado una fecha en <xref:System.Windows.Controls.DatePicker>.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate para  DatePicker  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DatePicker>.  
  
 [!code-xml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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