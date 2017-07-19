---
title: "Estilos y plantillas de Button | Microsoft Docs"
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
  - "Button [WPF], estilos y plantillas"
  - "ControlTemplate [WPF], Botón"
  - "partes [WPF], Botón"
  - "estados [WPF], Botón"
  - "estilos [WPF], Botón"
  - "plantillas [WPF], Botón"
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Estilos y plantillas de Button
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.Button>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de Button  
 El control <xref:System.Windows.Controls.Button> no tiene ningún elemento con nombre.  
  
## Estados de Button  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.Button>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Pressed|CommonStates|El control está presionado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|Focused|FocusStates|El control tiene el foco.|  
|Unfocused|FocusStates|El control no tiene el foco.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de Button  
 En el ejemplo siguiente, se muestra cómo definir un objeto <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 El ejemplo anterior utiliza uno o más de los siguientes recursos.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para obtener el ejemplo completo, vea [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)