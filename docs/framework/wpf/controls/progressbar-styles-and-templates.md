---
title: "Estilos y plantillas de ProgressBar | Microsoft Docs"
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
  - "ControlTemplate [WPF], ProgressBar"
  - "partes [WPF], ProgressBar"
  - "ProgressBar [WPF], estilos y plantillas"
  - "estados [WPF], ProgressBar"
  - "estilos [WPF], ProgressBar"
  - "plantillas [WPF], ProgressBar"
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Estilos y plantillas de ProgressBar
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.ProgressBar>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de ProgressBar  
 En la siguiente tabla se muestran los elementos con nombre del control <xref:System.Windows.Controls.ProgressBar>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|Indicador PART|<xref:System.Windows.FrameworkElement>|Objeto que indica el progreso.|  
|PART\_Track|<xref:System.Windows.FrameworkElement>|Objeto que define la ruta de acceso del indicador de progreso.|  
|PART\_GlowRect|<xref:System.Windows.FrameworkElement>|Objeto que embellece la barra de progreso.|  
  
## Estados de ProgressBar  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.ProgressBar>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|---------------------------|--------------------------------|-----------------|  
|Determinate|CommonStates|<xref:System.Windows.Controls.ProgressBar> informa del progreso según la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.|  
|Indeterminado|CommonStates|<xref:System.Windows.Controls.ProgressBar> informa del progreso genérico mediante un patrón de repetición.|  
|Valid|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> es `true`, tiene el control pero no tiene el foco.|  
  
## Ejemplo de ControlTemplate para ProgressBar  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ProgressBar>.  
  
 [!code-xml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
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