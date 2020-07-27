---
title: Estilos y plantillas de TextBox
description: Obtenga información sobre los estilos y las plantillas del control TextBox Windows Presentation Foundation. Modifique el ControlTemplate para dar al control una apariencia única.
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 0e15fd40f5590ee46da49cc6c0d5fb30e051f7e4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164729"
---
# <a name="textbox-styles-and-templates"></a>Estilos y plantillas de TextBox
En este tema se describen los estilos y las plantillas del <xref:System.Windows.Controls.TextBox> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="textbox-parts"></a>Elementos de cuadro de texto  
 En la tabla siguiente se enumeran las partes con nombre para el <xref:System.Windows.Controls.TextBox> control.  
  
|Parte|Tipo|Description|  
|-|-|-|  
|PART_ContentHost|<xref:System.Windows.FrameworkElement>|Elemento visual que puede contener un <xref:System.Windows.FrameworkElement> . El texto de <xref:System.Windows.Controls.TextBox> se muestra en este elemento.|  
  
## <a name="textbox-states"></a>Estados de TextBox  
 En la tabla siguiente se enumeran los Estados visuales del <xref:System.Windows.Controls.TextBox> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|ReadOnly|CommonStates|El usuario no puede cambiar el texto en <xref:System.Windows.Controls.TextBox> .|  
|Con foco|FocusStates|El control tiene el foco.|  
|Sin foco|FocusStates|El control no tiene el foco.|  
|Válido|ValidationStates|El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta tiene `true` el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta `true` tiene el control no tiene el foco.|  
  
## <a name="textbox-controltemplate-example"></a>Ejemplo de ControlTemplate de TextBox  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.TextBox> control.  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creación de una plantilla de un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
