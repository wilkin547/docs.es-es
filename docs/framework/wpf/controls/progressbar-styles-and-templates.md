---
title: Estilos y plantillas de ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099422"
---
# <a name="progressbar-styles-and-templates"></a>Estilos y plantillas de ProgressBar
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ProgressBar> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="progressbar-parts"></a>Partes de la barra de progreso  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ProgressBar> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|El objeto que indica el progreso.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|El objeto que define la ruta de acceso del indicador de progreso.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Objeto que embellishes la barra de progreso.|  
  
## <a name="progressbar-states"></a>Estados de la barra de progreso  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.ProgressBar> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Determinada|CommonStates|<xref:System.Windows.Controls.ProgressBar> informa del progreso según el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> propiedad.|  
|Indeterminado|CommonStates|<xref:System.Windows.Controls.ProgressBar> indica el progreso general con un patrón de repetición.|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="progressbar-controltemplate-example"></a>Ejemplo de ControlTemplate para ProgressBar  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ProgressBar> control.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Personalizar la apariencia de un control existente creando una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
