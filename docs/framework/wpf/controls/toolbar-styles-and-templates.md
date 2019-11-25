---
title: Estilos y plantillas de ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: a984311234386cb205d5db35f18a743ca535ff05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283656"
---
# <a name="toolbar-styles-and-templates"></a>Estilos y plantillas de ToolBar
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.ToolBar>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="toolbar-parts"></a>Elementos de barra de herramientas  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.ToolBar>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ToolBarPanel|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|Objeto que contiene los controles del <xref:System.Windows.Controls.ToolBar>.|  
|PART_ToolBarOverflowPanel|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|Objeto que contiene los controles que se encuentran en el área de desbordamiento del <xref:System.Windows.Controls.ToolBar>.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.ToolBar>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## <a name="toolbar-states"></a>Estados de la barra de herramientas  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.ToolBar>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="toolbar-controltemplate-example"></a>Ejemplo de ControlTemplate de ToolBar  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
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
