---
title: "Estilos y plantillas de Frame | Microsoft Docs"
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
  - "ControlTemplate [WPF], Fotograma"
  - "Frame [WPF], estilos y plantillas"
  - "partes [WPF], Fotograma"
  - "estados [WPF], Fotograma"
  - "estilos [WPF], Fotograma"
  - "plantillas [WPF], Fotograma"
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Estilos y plantillas de Frame
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.Frame>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de marco  
 En la siguiente tabla, se muestran los elementos con nombre del control <xref:System.Windows.Controls.Frame>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_FrameCP|<xref:System.Windows.Controls.ContentPresenter>|Área de contenido.|  
  
## Estados de marco  
 En la siguiente tabla, se muestran los estados visuales del control <xref:System.Windows.Controls.Frame>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate de Frame  
 En el ejemplo siguiente, se muestra cómo definir un objeto <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.Frame>.  
  
 [!code-xml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
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