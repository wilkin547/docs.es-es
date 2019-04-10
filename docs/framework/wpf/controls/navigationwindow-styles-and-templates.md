---
title: Estilos y plantillas de NavigationWindow
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 32d8aac99d40693e66c7b52a6c7d2c116d2f3baf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225812"
---
# <a name="navigationwindow-styles-and-templates"></a>Estilos y plantillas de NavigationWindow
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Navigation.NavigationWindow> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="navigationwindow-parts"></a>Partes de NavigationWindow  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Navigation.NavigationWindow> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_NavWinCP|<xref:System.Windows.Controls.ContentPresenter>|El área para el contenido.|  
  
## <a name="navigationwindow-states"></a>Estados de NavigationWindow  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Navigation.NavigationWindow> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="navigationwindow-controltemplate-example"></a>Ejemplo de ControlTemplate de NavigationWindow  
 Aunque este ejemplo contiene todos los elementos que se definen en el <xref:System.Windows.Controls.ControlTemplate> de un <xref:System.Windows.Navigation.NavigationWindow> de forma predeterminada, los valores específicos que deben considerarse ejemplos.  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Personalizar la apariencia de un control existente creando una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
