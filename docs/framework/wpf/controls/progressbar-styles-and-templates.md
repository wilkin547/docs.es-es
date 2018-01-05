---
title: Estilos y plantillas de ProgressBar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6809ce2f51af8a1baf535afa8fe80f4e5b5f53e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-styles-and-templates"></a>Estilos y plantillas de ProgressBar
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ProgressBar> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
## <a name="progressbar-parts"></a>Partes de la barra de progreso  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ProgressBar> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|El objeto que indica el progreso.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|El objeto que define la ruta de acceso del indicador de progreso.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Objeto que embellishes la barra de progreso.|  
  
## <a name="progressbar-states"></a>Estados de la barra de progreso  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ProgressBar> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Determinada|CommonStates|<xref:System.Windows.Controls.ProgressBar>informa del progreso tomando como base el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propiedad.|  
|Indeterminado|CommonStates|<xref:System.Windows.Controls.ProgressBar>indica el progreso general con un patrón de repetición.|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="progressbar-controltemplate-example"></a>Ejemplo de ControlTemplate de ProgressBar  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ProgressBar> control.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
