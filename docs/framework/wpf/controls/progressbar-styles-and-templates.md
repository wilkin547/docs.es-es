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
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283451"
---
# <a name="progressbar-styles-and-templates"></a>Estilos y plantillas de ProgressBar
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ProgressBar>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="progressbar-parts"></a>Elementos ProgressBar  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ProgressBar>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|Objeto que indica el progreso.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|Objeto que define la ruta de acceso del indicador de progreso.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|Objeto que adorna la barra de progreso.|  
  
## <a name="progressbar-states"></a>Estados de ProgressBar  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ProgressBar>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Determinada|CommonStates|<xref:System.Windows.Controls.ProgressBar> informa del progreso en función de la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.|  
|Determina|CommonStates|<xref:System.Windows.Controls.ProgressBar> informa del progreso genérico con un patrón de repetición.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="progressbar-controltemplate-example"></a>Ejemplo de ControlTemplate de ProgressBar  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ProgressBar>.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
