---
title: Estilos y plantillas de DocumentViewer
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: ac1dc4f74a8e8f3ad2e84c6d50239ec827306c28
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283532"
---
# <a name="documentviewer-styles-and-templates"></a>Estilos y plantillas de DocumentViewer
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.DocumentViewer>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="documentviewer-parts"></a>Elementos DocumentViewer  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.DocumentViewer>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.Controls.ScrollViewer>|El contenido y el área de desplazamiento.|  
|PART_FindToolBarHost|<xref:System.Windows.Controls.ContentControl>|El cuadro de búsqueda, en la parte inferior de forma predeterminada.|  
  
## <a name="documentviewer-states"></a>Estados de DocumentViewer  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.DocumentViewer>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="documentviewer-controltemplate-example"></a>Ejemplo de ControlTemplate de DocumentViewer  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DocumentViewer>.  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
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
