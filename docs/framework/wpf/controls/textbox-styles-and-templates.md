---
title: "Estilos y plantillas de TextBox | Microsoft Docs"
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
  - "ControlTemplate [WPF], TextBox"
  - "partes [WPF], TextBox"
  - "estados [WPF], TextBox"
  - "estilos [WPF], TextBox"
  - "plantillas [WPF], TextBox"
  - "TextBox [WPF], estilos y plantillas"
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Estilos y plantillas de TextBox
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.TextBox>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de TextBox  
 En la siguiente tabla, se muestran los elementos con nombre del control <xref:System.Windows.Controls.TextBox>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_ContentHost|<xref:System.Windows.FrameworkElement>|Elemento visual que puede contener un <xref:System.Windows.FrameworkElement>.  El texto del control <xref:System.Windows.Controls.TextBox> se muestra en este elemento.|  
  
## Estados de TextBox  
 En la siguiente tabla, se muestran los estados visuales del control <xref:System.Windows.Controls.TextBox>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|ReadOnly|CommonStates|El usuario no puede cambiar el texto de <xref:System.Windows.Controls.TextBox>.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de TextBox  
 En el ejemplo siguiente, se muestra cómo definir un objeto <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
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